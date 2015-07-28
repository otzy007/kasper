---
layout: post
title: !binary |-
  c3lzdGVtIHN0YXR1cyBzY3JpcHQgZm9yIGJvdC5pbQ==
joomla_id: 78
joomla_url: !binary |-
  c3lzdGVtLXN0YXR1cy1zY3JpcHQtZm9yLWJvdGlt
date: 2009-12-02 18:56:15.000000000 +02:00
tags: [status, script, bot.im]
---
<p>Here's another script for a bot. You get from it various status informations by executing commands as: du, free or netstats. This project isn't finished yet so it could have some bugs. Enough talk, here's the script:</p>

<p> </p>
<p>
<pre><code>
&lt;?php
///////////////////////////////////////////////////
//system status php script for bot.im
//created by otzy_007(Andrei G.) http://oprod.net
///////////////////////////////////////////////////

//the message recieved from the user
$msg = strtolower($_REQUEST["msg"]);
////////////////////////////////////////////////
//list of commands that can be executed
///////////////////////////////////////
//to add a new command just follow this sintax:
//
//case "command":
//     echo_line("command");
//break;
//
//where command is your command to be executed
/////////////////////////////////////////////// 
switch($msg)
{
  case "date":
        echo date("D M j G:i:s T Y");
  break;
  case "whoami":
        echo exec(whoami);
  break;
  case "who":
       echo exec(who);
  break;
  case "free":
        echo_line("free");
  break;
  case "procinfo":
        echo_line("procinfo");
  break;
  case "meminfo":
        echo_line("cat /proc/meminfo");
  break;
  case "df":
        echo_line("df");
  break;
  case "ps":
        echo_line("ps");
  break;
  case "uptime":
        echo_line("uptime");
  break;
  case "uname":
        echo_line("uname -a");
  break;
  case "mounts":
        echo_line("cat /proc/mounts");
  break;
  case "user":
        echo $_REQUEST['user'];
  break;
  case "netstat":
        echo_line("netstat");
  break;
  case "help":
        help();
  break;
  default:
        echo "For a list of avaible commands enter help";
  break;
}

function help(){
echo "Avaible commands: help, date, whoami, who,
 uname, uptime, ps, df, meminfo, procinfo, free, mounts, netstat";
}
function echo_line($command)
{ 

 exec($command, $line);

 for($i=0; $i<count($line); $i++)
 {
  echo "<br>";
  echo $line[$i];
  
}

}

?> 
</code></pre>
</p>
