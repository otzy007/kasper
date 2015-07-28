---
layout: post
title: !binary |-
  VHdpdHRlciBIYXNodGFnIEF1dG8tTGluaw==
joomla_id: 64
joomla_url: !binary |-
  dHdpdHRlci1oYXNodGFnLWF1dG8tbGluaw==
date: 2009-06-08 00:00:00.000000000 +03:00
tags: [Twitter, Hashtag]
---
<p>Here's a little script I've made for <a href="http://www.greasespot.net/">Greasemonkey</a> to link the hashtags to twitter's search.</p>
<p>You can download it from here: <a href="http://oprod.net/index.php/downloads/category/7-greasemonkey">http://oprod.net/index.php/downloads/category/7-greasemonkey</a></p>
<p>And here's the sourcecode:
<pre><code>
// ==UserScript==
// @name           Twitter Hashtag Auto-Link
// @namespace      http://oprod.net
// @description    Auto-Links Twitter Hashtags to twitter search
// @include        http://twitter.com/*
// @include        https://twitter.com/*
// ==/UserScript==

var entries, entry;

entries = document.evaluate(
    "//*[@class='entry-content']",
    document,
    null,
    XPathResult.UNORDERED_NODE_SNAPSHOT_TYPE,
    null);

for(var i = 0; i < entries.snapshotLength; i++) {
    entry = entries.snapshotItem(i);
    entry.innerHTML = entry.innerHTML.replace(/#([^ ]+)/g, '<a href="http://twitter.com/#search?q=%23$1" 
title="$1"  target="_blank">#$1</a>');
}
</code></pre>
</p>
