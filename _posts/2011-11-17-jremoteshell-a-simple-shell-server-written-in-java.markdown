---
layout: post
title: !binary |-
  SlJlbW90ZVNoZWxsOiBhIHNpbXBsZSBzaGVsbCBzZXJ2ZXIgd3JvdGUgaW4g
  SmF2YQ==
joomla_id: 94
joomla_url: !binary |-
  anJlbW90ZXNoZWxsLWEtc2ltcGxlLXNoZWxsLXNlcnZlci13cml0dGVuLWlu
  LWphdmE=
date: 2011-11-17 22:08:36.000000000 +02:00
tags: [JRemoteShell, Java, Shell]
---
<p>Here's a small shell server written in Java by me.</p>
<p> </p>
<p>It has basic features such as: ls, cd, head, mv, cp and also: get and put, to get/put files on the server.</p>
<p><strong>Please note that this application is not safe to use because it doesn't use encryption or authentication.</strong></p>
<p>To connect to the server you can use Putty with a raw connection or netcat:</p>
`nc host 8100`
<p>To use "get" or "put" for file transfer you must first type put or get followed by the name of the file and then connect to port 8101 using nc.</p>
<p>For get: ```nc host 8101 > file```</p>
<p>For put: ```nc host 8101 < get```</p>
<p> </p>
<p>Download JAR file: <a href="https://github.com/downloads/otzy007/JRemoteShell/JRemoteShell.jar.zip">https://github.com/downloads/otzy007/JRemoteShell/JRemoteShell.jar.zip</a></p>
<p>Github repository: <a href="https://github.com/otzy007/JRemoteShell" target="_blank">https://github.com/otzy007/JRemoteShell</a></p>
<p>Source snapshot:<a href="https://github.com/downloads/otzy007/JRemoteShell/otzy007-JRemoteShell-d66e2b9.zip"> https://github.com/downloads/otzy007/JRemoteShell/otzy007-JRemoteShell-d66e2b9.zip</a></p>
