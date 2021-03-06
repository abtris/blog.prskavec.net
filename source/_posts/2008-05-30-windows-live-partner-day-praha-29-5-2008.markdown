--- 
layout: post
title: Windows Live Partner Day - Praha 29. 5. 2008
published: true
meta: 
  _encloseme: "1"
  _edit_last: "1"
  _pingme: "1"
tags: 
- live.com
- microsoft
- php
type: post
status: publish
---
Včera se konala akce Microsoftu na podporu Live služeb. Jistě znáte Live.com a ostatní služby se rozšiřují. O svých mapových podkladech minulý týden Balmer tvrdí, že jsou v USA někdy mnohem přesnější než v Google Earth. Kdo se nemohl zůčastnit může se podívat <a href="http://www.livebox.cz/microsoft/1032376581/">na prezentace a časem i na záznamy</a>, taky je k dispozici program.

Jako vývojáře PHP mě zaujmulo několik věcí. Mnohé služby Live jsou nezávislé na programovacím jazyce na serveru, nemusíte být zrovna .Net programátoři, aby jste mohli používat. Většinou stačí HTML a Javascript (např. Virtual Earth a Gadgets). A v dalších službách jako je LiveID, Live Search nebo Silverlight je podporováno na serverové straně více jazyků včetně PHP. To také demonstroval <a href="http://php.vrana.cz">Jakub Vrána</a> svým příspěvkem o <a href="http://php.vrana.cz/webove-sluzby-v-php-xml-rpc-a-soap.php">Live Search volaném z PHP</a>.
<h3>LiveID</h3>
Pokud budete chtít použít LiveID na svých stránkách, tak si <a href="http://www.microsoft.com/downloads/details.aspx?FamilyId=24195B4E-6335-4844-A71D-7D395D20E67B&amp;displaylang=en">stáhněte SDK</a> pro PHP přímo od Microsoftu. Není to probém rozeběhnout během pár minut. Vyžaduje mhash rozšíření pro PHP. Aplikaci si zaregistrujte v <a href="https://msm.live.com/app/default.aspx">Application Center</a> a nezapomeňte, že aplikace potřebuje v registraci platnou URL adresu (Return URL). Někdy stačí si pomoci editací souboru hosts (c:/windows/system32/drivers/etc/hosts) kde za 127.0.0.1 localhost přidáte také vaší Return URL (která existuje v DNS).
<h3>Live Search</h3>
Pokud chcete sledovat, jak vám Live indexuje stránky, použijte <a href="http://webmaster.live.com">Webmaster Tools</a> obdobně jako u Googlu. Pokud nevíte, jak nastavit parametry pro vyhledávání, doporučuji <a href="http://dev.live.com/livesearch/sdk/">Live Search Interactive SDK</a>, kde si to můžete online vyzkoušet a pohrát si s tím.

<a href="http://blog.prskavec.net/wp-content/uploads/2008/05/image7.png"><img style="border-top-width: 0px;border-left-width: 0px;border-bottom-width: 0px;border-right-width: 0px" src="http://blog.prskavec.net/wp-content/uploads/2008/05/image-thumb7.png" border="0" alt="image" width="644" height="424" /></a>
<h3>Siverlight</h3>
Windows Live Streaming: <a href="http://silverlight.live.com">silverlight.live.com</a> poskytuje 10GB pro vaše videa. Je to zajímavá služba, ale maximální délka videa je 10 min (dáno poplatky v USA za streaming). Pro encoding se používá Expresson Encoder 2, zdarma je k dispozici těm co mají MSDN subscription.
