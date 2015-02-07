---
layout: post
title: "Docker cluster management"
date: 2015-02-07 18:09
comments: true
categories: docker
---


V poslední době se zabývám technologiemi pro řízení clusterů s docker konteinery.

Pokud by to někoho zajímalo, zkusím jsem shrnout s čím jsem se potkal a kde vidím možné využití.

Nástroje, které můžete použít cluster management:

- [Apache Messos](http://mesos.apache.org/) (java)
- [Docker Swarm](https://github.com/docker/swarm/) (golang)
- [CoreOS Fleet](https://coreos.com/using-coreos/clustering/) (golang)
- [Google Kubernetes](http://kubernetes.io/) (golang)

potom k tomu ješte patří některé frameworky pro Messos a to [Marathon](https://mesosphere.github.io/marathon/) a [Chronos](http://airbnb.github.io/chronos/).

Ještě potřebujete nástroj pro service discovery:

- [CoreOS Etcd](https://coreos.com/using-coreos/etcd/) (golang)
- [Hashicorp Consul](https://consul.io/) (golang)
- [Apache Zookeeper](http://zookeeper.apache.org/) (java)

Etcd používá Kubernetes a další projekty. Service discovery je potřeba pro management clusteru. Můžete použít stejně jednoduše i ostatní projekty.

Apache Messos umí pracovat s různorodým prostředím včetně Amazon ECS service. Framework Marathon vám potom slouží k pouštění dlouho běžících konteinerů pro aplikace a Chronos typicky pro batch processing například pro zpracování velkých dat. S Messosem musíte provozovat ZooKeeeper pro discovery service.

Protože se snažím Javě vyhnout a raději volím nástroje v jiných jazycích, kde mám větší znalosti. Pro discovery service clusteru bych raději použil Consul nebo Etcd. 

Google Kubernetes je poměrně vyspělý nástroj používaný pro Google Cloud a adaptovaný například RedHatem pro OpenShift V3. Tam mám trochu výhradu, že to nemá podporu pro více uživatelů a neumí pracovat s externím filesystémy co vím. Ale dá se používat na tvorbu dokonce hybridních clusterů mezi více poskytovateli (AWS, Google Cloud, OpenShift, fyzické stroje). 

Docker Swarm je nástroj pro řízení clusterů konteinerů přímo od Dockeru, ale kromě základních příkladů není k dispozici nic většího, poporuje několik discovery service (etcs, consul, zookeeper). Nevím o nikom, kdo by to používal ve větším měřítku.

CoreOS Fleet je [systemd](https://coreos.com/using-coreos/systemd/) a [etcd](https://coreos.com/using-coreos/etcd/) a nemám s ním zkušenosti vůbec žádné. Projekty kolem [CoreOS](https://coreos.com/). 

Stejně jako CoreOS snaží se o podobnou věc i [Project Atomic](http://www.projectatomic.io/) od RedHatu. Vytvořit základní systém pro práci s kontainery. 

Závěr je asi takový, že pokud budete chtít řídít vlastní cluster asi zvolíte buď Messos nebo Kubernetes. Osobně asi budu volit Kubernetes, co vy?
