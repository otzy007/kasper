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
Here's a small shell server written in Java by me.

It has basic features such as: ls, cd, head, mv, cp and also: get and put, to get/put files on the server.

<strong>Please note that this application is not safe to use because it doesn't use encryption or authentication.</strong>

To connect to the server you can use Putty with a raw connection or netcat:

`nc host 8100`

To use "get" or "put" for file transfer you must first type put or get followed by the name of the file and then connect to port 8101 using nc.

For get: ```nc host 8101 > file```

For put: ```nc host 8101 < get```

Download JAR file: <a href="https://github.com/downloads/otzy007/JRemoteShell/JRemoteShell.jar.zip">https://github.com/downloads/otzy007/JRemoteShell/JRemoteShell.jar.zip</a>

Github repository: <a href="https://github.com/otzy007/JRemoteShell" target="_blank">https://github.com/otzy007/JRemoteShell</a>

Source snapshot:<a href="https://github.com/downloads/otzy007/JRemoteShell/otzy007-JRemoteShell-d66e2b9.zip"> https://github.com/downloads/otzy007/JRemoteShell/otzy007-JRemoteShell-d66e2b9.zip</a>
