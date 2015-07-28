---
layout: post
title: !binary |-
  VmlkZW8gY29udmVydCBzY3JpcHQ=
joomla_id: 52
joomla_url: !binary |-
  dmlkZW8tY29udmVydC1zY3JpcHQ=
date: 2009-03-19 22:00:00.000000000 +02:00
tags: [viewtyconv, mencoder]
---
<p>Today I've made my account on <a href="http://snipt.net/">snipt</a> :) And my first contribution to the comunity is a video converter script to convert movies for  the LG KU990 Viewty phone. Here's the script:</p>
<pre><code>!/bin/bash

#convert movies into divx format for lg ku990 viewty

mencoder "$1" -ovc lavc -oac lavc -lavcopts acodec=libmp3lame:abitrate=128 \
-vf scale=400:240 -ffourcc DX50 -fps 23 -o "$2"</code></pre>
You can download it at: <a href="http://oprod.net/index.php/downloads/category/3-viewtyconv">http://oprod.net/index.php/downloads/category/3-viewtyconv</a>
