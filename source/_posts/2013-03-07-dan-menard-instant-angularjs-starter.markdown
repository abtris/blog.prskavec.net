---
layout: post
title: "Dan Menard - Instant AngularJS Starter"
date: 2013-03-07 21:20
comments: true
categories: review
---

V únoru 2013 vyšla první kniha o [AngularJS](http://www.angularjs.org) v nakladatelství [Packt Publishing](http://www.packtpub.com/angularjs-to-build-dynamic-web-applications/book), kterou jsem dostal, abych jí zhodnotil. 

[{% img center /images/AngualarJS_Starter_Cover.jpg "AngualarJS Starter - Cover" %}](http://www.packtpub.com/angularjs-to-build-dynamic-web-applications/book)

Trochu mě to překvapilo, protože čekám na knihu [AngularJS](http://shop.oreilly.com/product/0636920028055.do) od Brad Green a Shyam Seshadri, která bude v dubnu. Bude to zajímavé porovnání jak to autoři pojali.

Kniha Instant AngularJS Starter míří na začátečníky a má velmi jednoduchý Hello World a potom si vytvoříte aplikaci GuideBook. Nakonec je několik kapitol, které projdou hlavní věci v AngularJS a snaží se je vysvětlit celkem podrobně (Templates, Two-way databinding, Modules, Dependency Injection a Directives).

Kniha přijde celkem krátká a její obtížnost a věci jak předkládá mi nepřijdou úplně vhodné. Občas jsou chyby v názvosloví, ze začátku se přeskakují výrazy (např. filter), které potom lehce vysvětlí, ale třeba není vůbec ukázáno jak si vlastní [filter](http://docs.angularjs.org/guide/concepts#filters) napsat i když to považuji za velmi užitečné. 

Autor nepřidává komplexnost aplikace postupně, ale snaží se ji dát celou a části vysvětlit, což může být problém pochopit proč a jak co dělá a kde je ta motivace. Velmi podrobná je třeba kapitola o Dependency Injection až do detailů, které jsou myslím zbytečné a stačilo ukázat použití a možné chyby. Přitom základní věci [nejsou vysvětlené](http://docs.angularjs.org/guide/di). Vlastní vysvětlení a motivaci DI mi chybí, detaily implementace jsou v této knize úplně zbytečné a jeden [obrázek](http://docs.angularjs.org/guide/concepts) často vydá za víc než deset stránek v knize.

V two-way databinding mi chybělo vysvětlení [ngBind](http://docs.angularjs.org/api/ng.directive:ngBind) a [tečkové konvence](http://egghead.io/video/angularjs-the-dot/). Autor nevysvětlil sdílení dat mezi kontrolery a porozumění [isolate scope](http://egghead.io/video/angularjs-the-dot/) si nemyslím nebude úplně zřejmé i když se toho v direktivách autor dotkne, ale neklade na to tolik důrazů kolik si myslím, že si to zaslouží. 

Vynechání [ngResource](http://docs.angularjs.org/api/ngResource.$resource) a [promise](http://docs.angularjs.org/api/ng.$q) stejně jako, že se vůbec aplikace netestuje mi nepřijde úplně vhodné. Obzvláště jen mluvit o testování a nebo ukázat jak jednoduše a správně testovat mi přijde velký rozdíl. 

## Závěr
Kniha není drahá (6 EUR), ale přesto bych čekal více, ani přiložený kód neobsahuje více příkladů, zdrojové kódy nemají komentáře ani testy u sebe. 
Čtenář pokud si udělá [tutorial](http://docs.angularjs.org/tutorial), podívá se na [videa](http://egghead.io/) a prostuduje [FoodMe workshop](https://github.com/IgorMinar/foodme) udělá lépe než koupením této knihy.