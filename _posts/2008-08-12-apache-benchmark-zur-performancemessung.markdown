---
layout: post
status: publish
published: true
title: Apache Benchmark zur Performancemessung
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: Ein tolles Tool um Performancemessungen auf Webserver durchzuführen
wordpress_id: 49
wordpress_url: http://blog.azngeek.de/?p=49
date: !binary |-
  MjAwOC0wOC0xMiAxMjozODoxNSArMDIwMA==
date_gmt: !binary |-
  MjAwOC0wOC0xMiAxMDozODoxNSArMDIwMA==
categories:
- Apache
tags: []
comments: []
---
<p>Eine einfache und &uuml;beraus elegante Methode zur Performancemessung einer Website oder einfach nur eines Skriptes ist das bei einer Defaultinstallation von Apache beiligende Tool ab. Ich selber benutze Ubuntu und bereits &uuml;ber die Paketverwaltung ist ab mit Apache vorinstalliert. Man kann auch ganz einfach das Kommando &uuml;berall aus der Shell heraus aufrufen.</p>
<p>Folgender Befehl f&uuml;hrt das Skript 100 mal aus und gibt dann ein sch&ouml;nes Ergebnis zur&uuml;ck.</p>
<pre lang="ini">ab -c 10 -n 100 http:&#47;&#47;localhost&#47;projects&#47;myscript&#47;scriptname.php<&#47;pre><br />
Es st&ouml;rt eigentlich auch nicht wirklich, dass es kein grafisches Frontend daf&uuml;r gibt, da die Ausgabe auf das Minimalste beschr&auml;nkt ist. Die vollst&auml;ndige Dokumentation findet man auf der <a title="Apache ab Benchmarking Tool" href="http:&#47;&#47;httpd.apache.org&#47;docs&#47;2.0&#47;programs&#47;ab.html">Projektseite<&#47;a></p>
