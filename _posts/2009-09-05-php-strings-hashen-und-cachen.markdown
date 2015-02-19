---
layout: post
status: publish
published: true
title: PHP Strings hashen und cachen
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 240
wordpress_url: http://www.azngeek.de/?p=240
date: !binary |-
  MjAwOS0wOS0wNSAwMDozNjo0MCArMDIwMA==
date_gmt: !binary |-
  MjAwOS0wOS0wNCAyMjozNjo0MCArMDIwMA==
categories:
- php
- Entwicklung
tags:
- memcache
- apc
- hash
- md5
- caching
comments: []
---
<h1>Warum hashen und cachen?<&#47;h1><br />
Ohne lange Erkl&auml;rungen gehe ich direkt zu einem Beispiel. Gegeben ist eine URL inklusive viele Parameter. Wir wollen diese URL maskieren damit der User diese URL nicht sehen kann.</p>
<h2>Die base64_encode() Methode<&#47;h2></p>
<blockquote><p>Encodes the given <em><tt>data<&#47;tt><&#47;em> with base64.</p>
<p>This encoding is designed to make binary data survive transport through    transport layers that are not 8-bit clean, such as mail bodies.</p>
<p>Base64-encoded data takes about 33% more space than the original    data.<&#47;blockquote><br />
Base 64 eignet sich hervorragend dazu, Links zu maskieren. Es hat aber wie schon im Quote erw&auml;hnt einen gewaltigen Nachteil: Der Originalstring wird gr&ouml;&szlig;er!</p>
<p>Weiterhin hat base64 noch einen kleinen Nachteil. Einige Sonderzeichen werden nicht unterst&uuml;tzt. Daher m&uuml;ssen diese erst einmal rausgefilter werden.</p>
<pre lang="PHP">$link = "http:&#47;&#47;www.beispiel.tld&#47;link?param1=eins&amp;param2=zwei&amp;param3=drei";<br />
$encodedLink = strtr ( base64_encode ( $link ), '+&#47;=', '-_,' );<&#47;pre></p>
<h2>Die Memcache Methode<&#47;h2></p>
<blockquote><p>Memcache module provides handy procedural and object oriented interface    to memcached, highly effective caching daemon, which was especially    designed to decrease database load in dynamic web applications.<&#47;blockquote><br />
Super Sache, denn mit Memcache lassen sich mit der Methode Memcache::add() Variablen im Speicher ablegen. Die Methode add() nimmt zwei Argumente entgegen - key und value. Als Key bietet sich ein unique identifier an, zum Beispiel ein Hashtag.</p>
<pre lang="PHP">$link = "http:&#47;&#47;www.beispiel.tld&#47;link?param1=eins&amp;param2=zwei&amp;param3=drei";<br />
$md5 = md5($link);<br />
Memcache::add($md5, $value);<&#47;pre></p>
<h2>Die APC Methode<&#47;h2><br />
Auch APC bietet eine Methode an um Dateien direkt im Cache abzulagern. Die Funktionsweise von APC und Memcache sind oberfl&auml;chlich &auml;hnlich. Der Unterschied ist aber dass Memcache ein verteiltes Caching erm&ouml;glicht w&auml;hrend APC nur lokal cached. Der Zugriff auf APC ist daher sehr schnell. Es bietet sich besonders an wenn Werte oft ge&auml;ndert und gelesen werden.</p>
<p>PHP bietet von Haus an eine native Unterst&uuml;tzung f&uuml;r APC. Die funktion heisst in dem Fall apc_add() und nimmt auch wie bei Memcache::add() die Gleichen zwei Argumente entgegen: key und value.</p>
<pre lang="PHP">$link = "http:&#47;&#47;www.beispiel.tld&#47;link?param1=eins&amp;param2=zwei&amp;param3=drei";<br />
$md5 = md5($link);<br />
apc_add($md5, $value);<&#47;pre></p>
