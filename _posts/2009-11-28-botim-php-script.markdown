---
layout: post
title: !binary |-
  Ym90LmltIHBocCBzY3JpcHQ=
joomla_id: 77
joomla_url: !binary |-
  Ym90aW0tcGhwLXNjcmlwdA==
date: 2009-11-28 08:31:24.000000000 +02:00
tags: [bot.im, shell]
---
<p>After 6 months of no php coding at all, yesterday I've made a little script for a bot for twitter, jabber, yahoo messenger and other services using <a href="http://bot.im" target="_blank">bot.im</a>.The script is pretty simple, responds to some commands and also uses the exec() php command.</p>
<p>And here's the script:</p>
<pre><code>
&lt;?php

//simple php script for bot.im
//created by otzy_007(Andrei G.) http://oprod.net


//the message from the user
$msg = strtolower($_REQUEST["msg"]);

$part = explode("(", $msg);

//if there's an exec command execute it
//example: exec(whoami), exec(ps), exec(uptime)
if($part[0]=='exec'){
$part[1]=rtrim($part[1], ")"); 
echo exec($part[1]);
}
//else execute the other commands
else
{
switch($msg)
{
  case "date":
        echo date("D M j G:i:s T Y");
  break;
  case "hello":
        echo "Hi!";
  break;
  case "user":
        echo $_REQUEST['user'];
  break;
  case "help":
        help();
  break;
  default:
        echo "For a list of avaible commands enter help";
  break;
}
}
function help(){
echo "Avaible commands: help, date, hello, exec(\"command\") without quotes";
}

?></code></pre>
</br>
Download: <a href="http://oprod.net/index.php/downloads/category/8-php?download=17%3Abot.im-script">http://oprod.net/index.php/downloads/category/8-php?download=17%3Abot.im-script</a>
