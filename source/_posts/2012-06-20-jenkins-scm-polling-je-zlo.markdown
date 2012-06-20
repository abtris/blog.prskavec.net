---
layout: post
title: "Jenkins SCM polling je zlo!"
date: 2012-06-20 18:54
comments: true
categories: 
---
Moc jsem nechápal problémy, které řešil [Kohsuke Kawaguchi](http://kohsuke.org/2011/12/01/polling-must-die-triggering-jenkins-builds-from-a-git-hook/) na konci roku. Ale brzo jsem to měl zjistit. Před časem přišel za mnou kolega, že chce zkonfigurovat polling stylem popisovaným v článku. 

Polling jsme nastavili na 1x24h a máme git-update hook, který nám polling spustí po kommitu, kdy je potřeba. Ukázka git-update skriptu.

	REPOSITORY_BASENAME=$(basename "$PWD") 
	curl http://jenkins.firma.cz/jenkins/git/notifyCommit?url=ssh://git@git.firma.cz/$REPOSITORY_BASENAME

V poslední době nám performace jenkins serveru začala klesat a load serveru prudce stoupat. Začali jsme to řešit pomocí dalších volných strojů, které se k jenkins masteru připojovali jako slave node. Úspěšně jsme si vyzkoušeli na to použití pluginu [swarm](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin), který můžu doporučit. Vytvořili jsme RPM balík, který nainstalujeme na volný stroj a swarm se připojí k masteru a je plně nakonfigurovaný a k dispozici. Důležité je jen mít na slave nodes dost diskového prostoru, protože joby jsou dost často velké, obzvláště pokud jich máte velký počet. 

Abych se vrátil k SCM pollingu. Naši systémaci udělali analýzu nejvytíženějších repository v Gitu. A data mám udávají čas spotřebovaný na provedení všech činností po dobu 14 dní. Na grafu je vidět přehled podle repository.

{% img center /images/scmpolling/graph-01.png 'Prehled repository podle casu' %}

V dalším grafu je vidět potom rozložení podle zátěže jednotlivými klienty, jak stroji (převážně jenkins a slave nodes, uživatelé jsou v minoritě).

{% img center /images/scmpolling/graph-02.png 'Prehled repository podle uzivatele' %}

Poslední graf ukazuje počet přístupů do jednotlivých repository. Je potřeba podle toho upravit joby a jejich SCM polling.

{% img center /images/scmpolling/graph-03.png 'Prehled repository podle poctu pristupu' %}


Na hromadné změny SCM pollingu můžete úspěšně použít [Configuration Slicing Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Configuration+Slicing+Plugin), který vám práci usnadní. U nějvíce vytížených repository doporučili použít notifikace pomocí git-update hooku, případně to můžete udělat všude.

Výsledná zátěž stroje potom výrazně klesla potom co jsme upravili nastavení jak je vidět z grafů muninu.

{% img center /images/scmpolling/graph-04.png 'Prehled z munina' %}

Další doporučení a tipy triky z praxe se dozvíte na mém školení [Jenkins - jak na Continuous Integration v PHP a Javascriptu](http://bit.ly/k-ci).