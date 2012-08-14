---
layout: post
title: "angualarjs-templates"
date: 2012-08-14 21:40
comments: true
categories: javascript, angularjs
---

# Šablony v AngularJS

Pokud začínáte s [AngularJS](http://www.angularjs.org) je dobré pro aplikace použít [angular-seed](https://github.com/angular/angular-seed).

## Jednotlivé šablony v samostatných souborech

Šablony v angular-seed jsou rozděleny do samostatných souborů.

    app/
        js/
            app.js
        partials/
            partial1.html
            partial2.html

v app.js se potom načítají samostatně

    $routeProvider.when('/view1', {templateUrl: 'partials/partial1.html', controller: MyCtrl1});
    $routeProvider.when('/view2', {templateUrl: 'partials/partial2.html', controller: MyCtrl2});

Důležité je angularjs sice používa template cache, ale pro každý soubor si sáhne samostatně a udělá 2 requesty, což nemusí být optimální obzvláště pokud by jste měli 20 šablon.

Tento způsob se hodí při vývoji, aby jste měli šablony samostatně pro přehlednost.

## Inline šablony

V manuálu najdete jak vkládat [šablony](http://docs.angularjs.org/api/ng.directive:script), přímo do stránek pomocí script tagu.

    <script type="text/ng-template" id="partial1.html">
    <p>This is the partial for view 1.</p>
    </script>

Ty se dají použít velmi dobře. Pokud je to menší kód, ale jinak je lepší mít v samostatných souborech.

## Kombinace obou způsobů

Jak jsem to konzultoval s Vojto Jínou. Bereme, že pro development je dobré použít jednotlivé šablony samostatně, ale pro nasazení je dobré spojit šablony do jednoho souboru, aby jste ušetřili requesty.

Dá se použít například Grunt script pro vložení samostaných šablon z developmentu do inline šablon. Ukázkový script udělal Vojta Jína.

{% gist 3347478 %}

## Další možnosti

K tomu článku mě přivedl tento tweet.

{% blockquote @PatrikVotocek https://twitter.com/PatrikVotocek/statuses/235100756905189376 %}
Nevíte někdo jak v #angularjs docílit toho abych měl jeden (externí) soubor se všema šablonama?
{% endblockquote %}

To by předpokládalo řešení, že budeme mít soubor s šablonami a zkusíme ho načíst a zpracovat.

    <script src="all-templates.html" all-templates></script>

    module.directive('allTemplates', function() {
      return {
        terminal: true,
        compile: function(elm) {
          $compile(elm);
        };
      };
    });

a potom by jste to chtěli načíst, ale má to potíže protože se to nepřidá do DOMu.

    $http.get('all-templates.html').success(function(content) {
        $compile(content);
    });

Bohužel toto řešení se mi nepodařilo nějak uspokojivě rozchodit, aby se do DOMu šablona dostala, ale možná najdete řešení. Ale není to doporučované řešení. Zkuste se držet toho, že pro vývoj šablony dáte do samostatných souborů a pro vývoj si to nalinkujete dovnitř.

Pokud někdo rozchodíte poslední řešení dejte vědět v komentářích.

