---
layout: post
title: "Serverless jako něco víc než Docker"
date: 2016-06-06 13:50
comments: true
categories: serverless, aws
---

## Serverless

Zkusím popsat co je to serverless trochu lidsky. Samotné bez serveru je asi moc široký pojem. Pokud se podíváte na [Awesome Serverless](https://github.com/anaibol/awesome-serverless) najdete zde všechno možné od databází jako Firebase, Hoodie, které poskytují frontendovým aplikacím vše co potřebují k běhu, až k systémům, které vám umožňují více než stávající řešení na principu virtuálních serverů. O těch se hodně mluví a nejstarší z nich je AWS Lambda.

AWS příšlo se základním systémem v roce [2014](https://aws.amazon.com/blogs/aws/run-code-cloud/) a postupně to rozšiřovali, přidali v roce 2015 [AWS Gateway](https://aws.amazon.com/blogs/aws/amazon-api-gateway-build-and-run-scalable-application-backends/) a dnes je systém celkem dobře použitelný a vzniklo i několik frameworků ([Serverless](http://serverless.com/), [Apex](http://apex.run/) a [Flourish](http://thenewstack.io/amazon-debuts-flourish-runtime-application-model-serverless-computing/)).

Amazon, ale není jediný kdo má podobný systém. Dnes je k dispozici těch systémů několik.

- [IBM Bluemix OpenWhisk](http://www.ibm.com/cloud-computing/bluemix/openwhisk/)	(únor 2016, early access)
- [Google Cloud Functions](https://cloud.google.com/functions/) (únor 2016, alfa)
- [Microsoft Azure Functions](https://azure.microsoft.com/en-us/services/functions/) (březen 2016, in preview)

Jak vidíte kromě AWS, ale jsou ostatní spíše na začátku, ale za pár let v tom bude dobrá konkurence. Zvláště je důležité dořešit věci o které se snaží frameworky a to zjednodušit vývojáři nastavení samotné infrastruktury, verzování aplikace a prostředí do kterých nasazujete.

## Proč by mě to mělo zajímat?

Dnes se můžete na Lambdu koukat jako na něco co umí pustit kód v NodeJS, Pythonu nebo Javě. Ale hlavní síla je v kombinaci s dalšími AWS službami, ze kterých můžete vytvořit obří velmi dobře škálující aplikaci za velmi nízkých nákladů pro provoz resp. závislé na tom co opravdu aplikace dělá. Skoro zdarma dostanete neprodukční prostředí, které můžete mít stejné jako to produkční. Je potřeba samozřejmě aplikace navrhovat trochu jinak a ne pro každé použití je to správná cesta, ale na spoustu věcí to je zajímé.

Například si můžete udělat vlastní [GraphQL server](https://github.com/serverless/serverless-graphql-blog) nebo [Slack bot](https://aws.amazon.com/blogs/aws/new-slack-integration-blueprints-for-aws-lambda/).

Před nedávnem se konala i [specializovaná konference](http://serverlessconf.io/) na toto téma.

## PragueJS o Serverless
Pokud vás to zaujalo, přijďte si poslechnout nejen moji přednášku o Serverless na meetup 30.6.2016 do kanceláří STRV. Registrace je na [evetbrite](https://www.eventbrite.com/edit?eid=25563194202).
