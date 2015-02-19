---
layout: post
status: publish
published: true
title: Ubuntu 9.10 und ZendStudio bzw. Eclipse
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 265
wordpress_url: http://www.azngeek.de/?p=265
date: !binary |-
  MjAwOS0xMi0wNCAxNjoxMDozMCArMDEwMA==
date_gmt: !binary |-
  MjAwOS0xMi0wNCAxNToxMDozMCArMDEwMA==
categories:
- php
- Entwicklung
tags: []
comments:
- id: 1315
  author: Burak
  author_email: burak.yueksel@gmail.com
  author_url: ''
  date: !binary |-
    MjAwOS0xMi0yNSAxMjo0ODowNSArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0xMi0yNSAxMTo0ODowNSArMDEwMA==
  content: Danke f&uuml;r den Tip, hab mir 2 Std. gespart ;-)
- id: 1338
  author: admin
  author_email: donbosco.rulz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMC0wMy0xNiAxNToyNzowMSArMDEwMA==
  date_gmt: !binary |-
    MjAxMC0wMy0xNiAxNDoyNzowMSArMDEwMA==
  content: Gerne geschehen Burak.
- id: 2220
  author: Michel
  author_email: cnsbex2s@mail.com
  author_url: http://fsmzfOghE
  date: !binary |-
    MjAxNC0wNy0yNiAyMjowMTozNyArMDIwMA==
  date_gmt: !binary |-
    MjAxNC0wNy0yNiAyMTowMTozNyArMDIwMA==
  content: Thanks for a marvelous pointsg! I certainly enjoyed reading it, you are
    a great author.I will make sure to bookmark your blog and definitely will come
    back in the future. I want to encourage you to ultimately continue your great
    writing, have a nice morning!
---
<h1>Eclipse funktioniert nicht unter Ubuntu 9.10<&#47;h1><br />
Nein, so ganz richtig ist das nat&uuml;rlich nicht. Genauergesagt funktioniert nur eine kleine Sache nicht - n&auml;mlich der Linksklick mit der Maus. Das f&uuml;hrt dazu dass alle, die es gew&ouml;hnt sind mit einer grafischen Oberfl&auml;che zu arbeiten mit dem neuen Ubuntu so ziemlich erstaunt sein m&uuml;ssten. Der Bug ist bereits <a href="https:&#47;&#47;bugs.launchpad.net&#47;ubuntu&#47;+source&#47;gtk+2.0&#47;+bug&#47;442078">bekannt<&#47;a> (Buttons disappear or do not respond to mouse clicks in Eclipse) und sollte bald gefixt werden.</p>
<p>Mein pers&ouml;nliches Highlight bei dem Bug Log:</p>
<blockquote>
<table border="0">
<tbody>
<tr>
<td><a href="https:&#47;&#47;launchpad.net&#47;%7Egabegorelick">Gabe Gorelick<&#47;a> wrote             <span title="2009-10-05 19:00:24 UTC">on 2009-10-05<&#47;span>:<&#47;td></p>
<td><a href="https:&#47;&#47;bugs.launchpad.net&#47;ubuntu&#47;+source&#47;eclipse&#47;+bug&#47;443004&#47;comments&#47;4"> #4<&#47;a><&#47;td><br />
<&#47;tr><br />
<&#47;tbody><&#47;table><br />
Can you provide a screenshot of the bug<&#47;blockquote></p>
<h2>Der Workaround f&uuml;r das Button Problem<&#47;h2><br />
Man lege einfach ein neues Shell Script an dass man irgendwo platziert und dann aufruft.</p>
<pre lang="BASH">#!&#47;bin&#47;sh<br />
export GDK_NATIVE_WINDOWS=1<br />
&#47;yourpath&#47;ZendStudio<&#47;pre><br />
Das wars auch schon. Leider hat mich das ganze 2 Stunden gekostet! Ich hab ja erst gedacht der Grafikkartentreiber w&auml;re es gewesen! Wie immer, wenn es hilfreich war oder ihr wisst wie man es noch leichter l&ouml;sen kann, einfach einen Kommentar hinterlassen.</p>
