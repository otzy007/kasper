---
layout: post
title: !binary |-
  TmVlZCBmb3IgU3BlZWQgVW5kZXJncm91bmQgMiB2aWEgb3BlbnZw
joomla_id: 49
joomla_url: !binary |-
  bmVlZC1mb3Itc3BlZWQtdW5kZXJncm91bmQtMi12aWEtb3BlbnZw
date: 2008-08-12 00:00:00.000000000 +03:00
tags: [Need for Speed Underground 2, OpenVPN, Multiplayer]
---
<p>I just hate hamachi because when I want to play a game with my friends on the internet it just doesn't work, especially with Need for Speed Underground 2. So I was thinking one day that I can make my own vpn network. I choosed <a href="http://openvpn.net/">openvpn</a> because it's free and easy to configure.<a href="http://openvpn.net/index.php/documentation/howto.html#quick"> Here</a> you will find a tutorial how to install and configure it. First you'll have to Generate the master Certificate Authority (CA) with wich you will sign clients and server certificates. I've done this in my <a href="http://slackware.com" target="_blank">Slackware 12.1</a> Linux distribution with:</p>
<pre><strong><blockquote>./vars<br />./clean-all<br />./build-ca</blockquote></strong></pre>
<p>from my /usr/doc/openvpn-2.0.9/easy-rsa/2.0/ The directory might not be the same in your Linux distro. Also you can make this in Windows with the commands:</p>
<pre><strong><blockquote>vars<br />clean-all<br />build-ca</blockquote></strong></pre>
<p> </p>
<p>After that I've generated server's certificate with:</p>
<pre><strong><blockquote>./build-key-server server</blockquote></strong></pre>
<p> </p>
<p>or in Windows with:</p>
<p> </p>
<pre><strong><blockquote>build-key-server server</blockquote></strong></pre>
<p> </p>
<p>and also the certificates for the clients:</p>
<p> </p>
<pre><strong><blockquote>./build-key client1</blockquote></strong></pre>
<p> </p>
<p>in Windows:</p>
<pre><strong><blockquote>build-key client1</blockquote></strong></pre>
<p> </p>
<p>after that you will have to Generate Diffie Hellman parameters with:</p>
<pre><strong><blockquote>./build-dh</blockquote></strong></pre>
<p> </p>
<p>in Windows:</p>
<pre><strong><blockquote>build-dh</blockquote></strong></pre>
<p> </p>
<p>Here's a explanation of the generated files:</p>
<p> </p>
<table border="1" cellspacing="0" cellpadding="8">
<tbody>
<tr>
<td><strong>Filename</strong></td>
<td><strong>Needed By</strong></td>
<td><strong>Purpose</strong></td>
<td><strong>Secret</strong></td>
</tr>
<tr>
<td>ca.crt</td>
<td>server + all clients</td>
<td>Root CA certificate</td>
<td>NO</td>
</tr>
<tr>
<td>ca.key</td>
<td>key signing machine only</td>
<td>Root CA key</td>
<td>YES</td>
</tr>
<tr>
<td>dh{n}.pem</td>
<td>server only</td>
<td>Diffie Hellman parameters</td>
<td>NO</td>
</tr>
<tr>
<td>server.crt</td>
<td>server only</td>
<td>Server Certificate</td>
<td>NO</td>
</tr>
<tr>
<td>server.key</td>
<td>server only</td>
<td>Server Key</td>
<td>YES</td>
</tr>
<tr>
<td>client1.crt</td>
<td>client1 only</td>
<td>Client1 Certificate</td>
<td>NO</td>
</tr>
<tr>
<td>client1.key</td>
<td>client1 only</td>
<td>Client1 Key</td>
<td>YES</td>
</tr>
<tr>
<td>client2.crt</td>
<td>client2 only</td>
<td>Client2 Certificate</td>
<td>NO</td>
</tr>
<tr>
<td>client2.key</td>
<td>client2 only</td>
<td>Client2 Key</td>
<td>YES</td>
</tr>
<tr>
<td>client3.crt</td>
<td>client3 only</td>
<td>Client3 Certificate</td>
<td>NO</td>
</tr>
<tr>
<td>client3.key</td>
<td>client3 only</td>
<td>Client3 Key</td>
<td>YES</td>
</tr>
</tbody>
</table>
<p> </p>
<p>Now you will need to edit your configuration files. You can find a examples at: <a href="http://openvpn.net/index.php/documentation/howto.html#examples" target="_blank">http://openvpn.net/index.php/documentation/howto.html#examples</a> Just copy them into the server and the client and edit them with the right server address and certificates path. In windows you need to save them to .ovpn extension.</p>
<p> </p>
<p>To play Need for Speed Underground 2 you will also need nfsu2rely which you can found at: <a href="http://www.csc.liv.ac.uk/~greg/nfsu2relay.html" target="_blank"> http://www.csc.liv.ac.uk/~greg/nfsu2relay.html</a> <br />You will need nfs2relay only for the host PC. You will also need to know the IPs from the PCs in the network. nfsu2relay will be launched with command:</p>
<p> </p>
<pre><strong><blockquote>nfsu2relay ip1 ip2 ip3 ... ip n</blockquote></strong></pre>
<p> </p>
<p>example:</p>
<pre><strong><blockquote>nfsu2relay 10.8.0.1 10.8.0.6</blockquote></strong></pre>
<p> </p>
<p>Then start Need for Speed Underground 2 and enjoy <img src="http://www.pic4ever.com/images/wassat.gif" border="0" alt="B-)" /></p>
<p>PS: You can use the Virtual Private Network (VPN) not only to play Need for Speed Underground 2, but also other games that could be played in a Local Area Network (LAN) like  Need for Speed Most Wanted, Red Alert 2 or Call of Duty Modern Warfare.</p>
