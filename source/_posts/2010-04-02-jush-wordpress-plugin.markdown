--- 
layout: post
title: JUSH Wordpress plugin
published: true
meta: 
  _encloseme: "1"
  _edit_last: "1"
  _pingme: "1"
tags: 
- jush
- wordpress
type: post
status: publish
---
Pokud chcete použít ve Wordpressu <a href="http://php.vrana.cz/vytvareni-odkazu-do-dokumentace.php">odkazy do dokumentace</a> pomocí <a href="http://jush.sourceforge.net/">JUSH</a>, můžete použít <a href="http://github.com/abtris/jushplugin">plugin do Wordpressu</a>.

<strong>Ukázka:</strong>
<pre class="jush">
&lt;table onclick="alert(this.rows.length);" cellspacing="0" cellpadding="2"&gt;
&lt;meta http-equiv="Content-Type: text/html"&gt;
</pre>

<pre class="jush-php">
mail("", "", "", "From:")
ini_set("display_errors", true)
</pre>
<pre class="jush-sql">
SELECT NOW() FROM `table` WHERE `id` > 22 GROUP BY `text` ORDER BY `name`
</pre>
