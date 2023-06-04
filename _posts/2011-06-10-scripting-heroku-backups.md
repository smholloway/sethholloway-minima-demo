---
layout: post
title: Scripting Heroku backups
alias: /blog/2011/06/10/scripting-heroku-backups/
categories:
- Internet
tags:
- backup
- heroku
- rails
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
I was looking for a way to backup applications on Heroku and found a few options. There's a Rails plugin that stores your backups on Amazon S3 (<a title="Heroku S3 Backup plugin" href="https://github.com/edavis10/heroku_s3_backup">https://github.com/edavis10/heroku_s3_backup</a>), but I am satisfied with local backups.

So I updated an existing solution (<a title="Ben Scheirman's blog" href="http://flux88.com/2010/02/scripting-heroku-backups/">http://flux88.com/2010/02/scripting-heroku-backups/</a>) based on Heroku's updated documentation (<a title="Heroku Docs: pgbackups" href="http://devcenter.heroku.com/articles/pgbackups">http://devcenter.heroku.com/articles/pgbackups</a>).


<pre># lib/tasks/backup.rake

# Create a backup of a Rails application deployed to Heroku
# Technique taken from Ben Scheirman - http://flux88.com/2010/02/scripting-heroku-backups/
# Place file in lib/tasks/backup.rake (replace your_app_name with your application's Heroku name)
# Invoke using rake your_app_name:backup
# Dependencies: the heroku gem, the pgbackups heroku addon
namespace :your_app_name do
	desc 'Captures a heroku backup. Ensure you have the heroku gem and pgbackups addon installed\n
				gem install heroku &amp;&amp; heroku addons:add pgbackups'

	task :backup do
		# capture the backup bundle
		timestamp = `date -u '+%Y-%m-%d-%H-%M'`.chomp
		bundle_name = "your_app_name-#{timestamp}"
		puts "Capturing bundle #{bundle_name}..."
		`heroku pgbackups:capture --app your_app_name '#{bundle_name}'`

		# download &amp; destroy the bundle we just captured
		puts "Downloading bundle #{bundle_name}.dump"
		backup_url = `heroku pgbackups:url`
		`curl -o '#{bundle_name}'.dump '#{backup_url}'`

		# move the backup
		puts "Moving bundle to backups/#{bundle_name}.dump"
		`mkdir backups/`
		`mv '#{bundle_name}'.dump backups/#{bundle_name}.dump`
	end
end</pre>
I've also uploaded the file to my github account: <a title="Seth Holloway's GitHub" href="https://github.com/smholloway/miscellaneous/blob/master/rails/backup.rake">https://github.com/smholloway/miscellaneous/blob/master/rails/backup.rake</a>

There are a lot of things you could do to extend this further; for example, you could create a cron job to run the task periodically or schedule a few minutes every week to make the backups.

Let me know if you can improve this or if you find it useful.
