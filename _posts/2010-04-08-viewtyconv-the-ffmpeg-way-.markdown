---
layout: post
title: !binary |-
  dmlld3R5Y29udiAodGhlIGZmbXBlZyB3YXkp
joomla_id: 86
joomla_url: !binary |-
  dmlld3R5Y29udi10aGUtZmZtcGVnLXdheS0=
date: 2010-04-08 08:49:19.000000000 +03:00
tags: [viewtyconv, DivX, Linux, FFmpeg]
---
<p>Here's the new viewtyconv script. It can be used to convert movies into DivX format for LG KU990 Viewty or similar phones from a Bash Shell. Now it's using [[ffmpeg]], no longer [[mencoder]]. To use this script you'll need to have installed <a href="http://ffmpeg.org/" target="_blank" title="ffmpeg">ffmpeg</a> and also <a href="http://lame.sourceforge.net/" target="_blank" title="lame">lame</a>. Ffmpeg must be configured with --enable-libmp3lame, otherwise the script will not work.</p>
<p>
<pre><code>#!/bin/bash
#
#by otzy_007 http://oprod.net 
#
ffmpeg -i $1 -vcodec mpeg4 -s 400x240 -acodec libmp3lame -ab 128k -vtag DIVX $2</code></pre>
</p>
<p>You can also download the scripts from here: <a href="index.php/downloads/category/3-viewtyconv">http://oprod.net/index.php/downloads/category/3-viewtyconv</a></p>
