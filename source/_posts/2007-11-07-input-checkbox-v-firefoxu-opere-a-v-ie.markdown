--- 
layout: post
title: "Input checkbox v Firefoxu, Ope\xC5\x99e a v IE"
published: true
meta: 
  _use_texy: "1"
  _edit_last: "1"
tags: 
- ff
- forms
- ie
- javascript
- opera
type: post
status: publish
---
Nedávno jsem řešil celkem jednoduchou věc, ve formuláři byl checkbox, který při změně měl část formuláře schovat.
<pre name='code' class="php">...
&lt;input type="checkbox" onChange="zmen()" /&gt;
...</pre>
Celkem triviální s tím rozdílem, že to nefunguje v Internet Exploreru (zkoušel jsem IE7). Prostudoval jsem na MSDN dokumentaci a tam jsem se dočel, že metodu onChange sice IE podporuje, ale jen pro type='text'.
<pre name='code'  class="php">...
&lt;input type="checkbox" onClick="zmen()" /&gt;
...</pre>
Tak jsem si řekl, že metodu onChange nahradím onClick a mám vyhráno, ale ouvej, to zase nefungovalo ve Firefoxu a Opeře. Proto detekuji IE a podle toho <a href="http://smarty.php.net">Smarty</a> rozhodí možnost na onChange nebo onClick. Osobně si myslím, že onChange je logická, netuším proč v IE podpora chybí.
<pre  name='code' class="php">// Detekce IE
$ie = strpos($_SERVER["HTTP_USER_AGENT"], 'MSIE') ? true : false;
$ie = strpos($_SERVER["HTTP_USER_AGENT"], 'Opera') ? false : $ie;

if($ie)
{
$smarty-&gt;assign('ie', true);
}
else
{
$smarty-&gt;assign('ie', false);
}</pre>
