---
layout: post
title: Installing the Google Predictions API in R
alias: /blog/2012/03/25/installing-the-google-predictions-api-in-r/
categories:
- technical
tags:
- predictions
- r
- statistics
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _oembed_f9b901cfe862452418e143d022af5658: ! '{{unknown}}'
  _oembed_72e1549b9033ee9e275124ba30eb278f: ! '{{unknown}}'
  _oembed_2e7f630b0b7f5ae378bfaf2f72137e07: ! '{{unknown}}'
  _oembed_dd91902908de6f59c7fe4b8b9f3b5a8f: ! '{{unknown}}'
  _oembed_d1be682d448da9daa4bd9694f8a8e90a: ! '{{unknown}}'
  _oembed_e6dfd609185608a1b7e7268f6033425c: ! '{{unknown}}'
  _oembed_8d648f64d6e92122cb89fcb06b74b5c2: ! '{{unknown}}'
  _oembed_dea24f80b050579360e83c54914cdcee: ! '{{unknown}}'
  _oembed_5d8059cff8f28d4e07513eda15f00abd: ! '{{unknown}}'
  _oembed_08a5c81e64e7befbfea406a6f8aa21fa: ! '{{unknown}}'
  _oembed_f74c948007f77d85374d360114974b95: ! '{{unknown}}'
  _oembed_4d801146872a7ab2482dd2040c562a43: ! '{{unknown}}'
  _oembed_37bd3abb731f3a0ac22b48e4580ebf9e: ! '{{unknown}}'
  _oembed_abaf7691eecd86d7e41860db5f0a173c: ! '{{unknown}}'
  _oembed_627031442cf46775325360fef676b81e: ! '{{unknown}}'
  _oembed_653dfd6842b9a7fb0fff030290b30ff7: ! '{{unknown}}'
  _oembed_72ab4d8df3300cab0a435a7ac53a7036: ! '{{unknown}}'
  _oembed_831b1b6fa2b1bfbf3bdadfeefe9b9a65: ! '{{unknown}}'
  _oembed_79780e44d5f15506cca5601c5a8739f2: ! '{{unknown}}'
  _oembed_c5ad00cdaa059f9681ee4087f06bc1ec: ! '{{unknown}}'
---
Note: This post got buried and I never posted it. I haven't played with R in several months, so I'm not sure if this works anymore.



This assumes you have R downloaded and installed.

Download, install, and configure GSUtil (http://code.google.com/apis/storage/docs/gsutil_install.html)

Load R. You should see an ugly console :) In the window type
<pre>install.packages(c("RCurl", "rjson"))</pre>
You will be prompted to select a mirror; find something close to you and continue.

You might be frustrated that there's no success message:
<pre>trying URL 'http://www.revolution-computing.com/cran/bin/macosx/leopard/contrib/2.13/rjson_0.2.5.tgz'
Content type 'application/x-gzip' length 133138 bytes (130 Kb)
opened URL
==================================================
downloaded 130 Kb

The downloaded packages are in
	/var/folders/I3/I3YZ8e5tGOK9CY9LQ98ix++++TI/-Tmp-//RtmpFrtdp3/downloaded_packages</pre>
However, if you fail there will be an error message:
<pre>&gt; install.packages("seth", dependencies = TRUE)
Warning message:
In getDependencies(pkgs, dependencies, available, lib) :
  package ‘seth’ is not available (for R version 2.13.0)</pre>
<pre>&gt; install.packages("googlepredictionapi_0.1.tar.gz", repos=NULL, type="source")
Warning: invalid package ‘googlepredictionapi_0.1.tar.gz’
Error: ERROR: no packages specified
Warning message:
In install.packages("googlepredictionapi_0.1.tar.gz", repos = NULL,  :
  installation of package 'googlepredictionapi_0.1.tar.gz' had non-zero exit status</pre>
Download the Google Predictions API for R

https://code.google.com/p/google-prediction-api-r-client/

Install it
<pre>$ mkdir -p ~/R/library</pre>
<pre>$ mv googlepredictionapi_0.1.tar.gz ~/R/library/</pre>
<pre>$ R_LIBS_USER="~/R/library"</pre>
<pre>$ echo 'R_LIBS_USER="~/R/library"' &gt;  $HOME/.Renviron</pre>

<pre>R CMD INSTALL ~/R/library/googlepredictionapi_0.1.tar.gz</pre>
<pre></pre>
Source your libraries
<pre>library(rjson)
library(RCurl)
library(googlepredictionapi)</pre>
Some useful links
http://mjaniec.blogspot.com/2011/05/google-prediction-api-v12-for-r.html
https://code.google.com/p/google-prediction-api-r-client/
http://code.google.com/p/r-google-prediction-api-v12/

http://csg.sph.umich.edu/docs/R/localpackages.html



 * Load R *Note:* You will see an ugly console.
 * Install the pre-reqs

    > install.packages(c("RCurl", "rjson"))

 * Note: If you have not installed a package from CRAN before, You will  be prompted to select a mirror; find something close to you and continue.
 * Note: A successful install will not yield a success message--it will simply not show an error message.

 * Download, install, and configure GSUtil: <a href="http://code.google.com/apis/storage/docs/gsutil_install.html">http://code.google.com/apis/storage/docs/gsutil_install.html</a>
 * Download the Google Predictions API for R from <a href="https://code.google.com/p/google-prediction-api-r-client/">https://code.google.com/p/google-prediction-api-r-client/</a>
 * Install the plugin *Note:* I had to do it from the command line because the install failed inside R

    $ R CMD INSTALL your/path/to/googlepredictionapi_0.1.tar.gz

 * Now, you should be able to restart R and see the API listed in the Package Manager
 * From here we source our libraries

    > library(rjson)
    > library(RCurl)
    > library(googlepredictionapi)

 * If the data is already in your Google Storage account, you can begin training the model. I do not have data in GS yet, so I've stopped here.
