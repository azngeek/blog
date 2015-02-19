---
layout: post
status: publish
published: true
title: Profiling in PHP mit xdebug
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: Techniken und Tools, um den Flaschenhals in PHP basierten Applikationen zu
  finden und zu beheben.
wordpress_id: 34
wordpress_url: http://blog.azngeek.de/?p=34
date: !binary |-
  MjAwOC0wNy0xMCAyMTo0MTowMiArMDIwMA==
date_gmt: !binary |-
  MjAwOC0wNy0xMCAxOTo0MTowMiArMDIwMA==
categories:
- php
tags: []
comments: []
---
<p>Neulich erst in der Arbeit: Verschiedene Anwendungen laufen auf dem Server, um die Last nicht unn&ouml;tig auf einem Server zu haben, werden Anfragen auf verschiedene Server verteilt, dennoch gibt es sp&uuml;rbare Verz&ouml;gerungen in der Ausf&uuml;hrung. Was nun?</p>
<p>Machen wir mal einen kleinen Sprung abseits des Geschehens. Innerhalb weniger Jahren hat sich PHP zu den etabliertesten Sprachen in der Webentwicklung entwickelt und ist meiner Meinung nach auch der de-facto Standard. Anf&auml;nglichst als kleine Skriptsprache bel&auml;chelt, haben umfangreiche PHP Anwendungen nicht selten mehrere tausend Zeilen Code. Nicht erst durch das Verwenden von Frameworks skaliert PHP hervorragend mit zunehmender Komplexibilit&auml;t, doch eins haben alle Programmiersprachen gemeinsam. Um so h&ouml;her die Codedichte um so schwieriger wird das Debugging in PHP.</p>
