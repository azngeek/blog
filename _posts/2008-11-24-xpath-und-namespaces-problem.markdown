---
layout: post
status: publish
published: true
title: XPath und Namespaces Problem
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 81
wordpress_url: http://blog.azngeek.de/?p=81
date: !binary |-
  MjAwOC0xMS0yNCAxOToyODo1MyArMDEwMA==
date_gmt: !binary |-
  MjAwOC0xMS0yNCAxNzoyODo1MyArMDEwMA==
categories:
- php
- Entwicklung
tags:
- php
- xpath
comments: []
---
<p>XPath ist ja eine ganz tolle Sache, wenn es doch mal auch funktionieren w&uuml;rde wie man es sich so w&uuml;nscht. F&uuml;r die t&auml;gliche Arbeit ist XPath zum Teil aber mehr Frust als Vergn&uuml;gen, denn oftmals funktioniert XPath anscheinend nicht. Im folgenden Beispiel m&ouml;chte ich mir zum Beispiel alle Superhelden anzeigen lassen.</p>
<pre lang="XML" line="1">
<p>superhelden.xml</p>
<p><superhelden><br />
<held><br />
<name>Batman<&#47;name><br />
<beschreibung>Der dunkler Ritter<&#47;beschreibung><br />
<f&auml;higkeiten>Hat keine Superf&auml;higkeiten<&#47;f&auml;higkeiten><br />
<bild>batman.jpg<&#47;bild><br />
<&#47;held><br />
<held><br />
<name>Superman<&#47;name><br />
<beschreibung>Kommt von Krypton und hat zu enge Str&uuml;mpfe an<&#47;beschreibung><br />
<f&auml;higkeiten>Laseraugen, Superkraft...<&#47;f&auml;higkeiten><br />
<bild>superman.png<&#47;bild><br />
<&#47;held><br />
<held><br />
<name>Hulk<&#47;name><br />
<beschreibung>Gr&uuml;nes Monster mit lila Shorts<&#47;beschreibung><br />
<f&auml;higkeiten>Ist wahnsinnig stark wenn es w&uuml;tend wird. Arghhhh<&#47;f&auml;higkeiten><br />
<bild>incredible-hulk.jpg<&#47;bild><br />
<&#47;held><br />
<&#47;superhelden></p>
<p><&#47;pre></p>
<pre lang="java" line="1">
<p>$xml = &ldquo;superhelden.xml&rdquo;;</p>
<p>&#47;&#47; gib mir alle helden</p>
<p>$heroes = $xml->xpath(&rsquo;&#47;&#47;helden&rsquo;);</p>
<p><&#47;pre></p>
<p>In diesen Fall bekomme ich nun alle Helden ausgegeben. Doch wo ist nun das Problem? Nehmen wir mal an, die Helden geh&ouml;ren zu einer bestimmten Fraktion, sagen wir mal hier den Guten, so k&ouml;nnte man das nat&uuml;rlich jedem Helden explizit zuteilen. Da wir aber nun wissen dass sowohl Batman, Superman als auch Hulk gut sind, deklarieren wir das doch ganz einfach an den Anfang des XML-Dokumentes.</p>
<p>So, unsere Superhelden sind auch schon im Web 2.0 angekommen und haben sich eine tolle Domain gesichert. Da diese auch tolle Praktikanten im SEO haben, nennen wir diesen Namespace einfach mal superhelden.com&#47;fraktion&#47;gut.</p>
<p>Schaut dann folgenderma&szlig;en aus:</p>
<pre lang="XML" line="1">
<p>superhelden_gut.xml</p>
<p><superhelden xmlns=&rdquo;http:&#47;&#47;www.superhelden.com&#47;fraktion&#47;gut&rdquo;><br />
<held><br />
<name>Batman<&#47;name><br />
<beschreibung>Der dunkler Ritter<&#47;beschreibung><br />
<f&auml;higkeiten>Hat keine Superf&auml;higkeiten<&#47;f&auml;higkeiten><br />
<bild>batman.jpg<&#47;bild><br />
<&#47;held><br />
<held><br />
<name>Superman<&#47;name><br />
<beschreibung>Kommt von Krypton und hat zu enge Str&uuml;mpfe an<&#47;beschreibung><br />
<f&auml;higkeiten>Laseraugen, Superkraft...<&#47;f&auml;higkeiten><br />
<bild>superman.png<&#47;bild><br />
<&#47;held><br />
<held><br />
<name>Hulk<&#47;name><br />
<beschreibung>Gr&uuml;nes Monster mit lila Shorts<&#47;beschreibung><br />
<f&auml;higkeiten>Ist wahnsinnig stark wenn es w&uuml;tend wird. Arghhhh<&#47;f&auml;higkeiten><br />
<bild>incredible-hulk.jpg<&#47;bild><br />
<&#47;held><br />
<&#47;superhelden></p>
<p><&#47;pre></p>
<p>So nun f&uuml;hren wir mal das PHP Skript nochmal aus. Ich kann jetzt schon behaupten, dass nichts zur&uuml;ckkommen wird. Das liegt daran, dass XPath versucht, alle Helden zur&uuml;ckzugeben, die keinen Namespace zugeordnet sind. Bl&ouml;des XPath, was w&auml;re denn, wenn Commissioner Gordon versuchen w&uuml;rde, Batman aus der Liste zu extrahieren, XPath das aber nicht weil es den vorgegebenen Namespace nicht erkennt? Ganz richtig, alles im Arsch. Auch das Skript.</p>
<pre lang="java" line="1">
<p>$xml = &ldquo;superhelden.xml&rdquo;;</p>
<p>&#47;&#47; gib mir alle helden</p>
<p>$heroes = $xml->xpath(&rsquo;&#47;&#47;helden&rsquo;);</p>
<p><&#47;pre></p>
<p>Die L&ouml;sung ist ganz einfach und nennt sich Namespace-Prefix Mapping. Auf gut deutsch &uuml;bersetzt bedeutet das, dass der Namespace mit PHP registriert werden muss.  XPath muss also erfahren, in welchen Namespace es nach den Helden zu suchen hat.</p>
<pre lang="java" line="1">
<p>$xml = &ldquo;superhelden.xml&rdquo;;</p>
<p>&#47;&#47; namespace zum debuggen ausgeben</p>
<p>$namespaces = $this->_xml->getNamespaces(true);</p>
<p>&#47;&#47; gibt aus: array([0] => &lsquo;www.superhelden.com&#47;fraktion&#47;gut&rsquo;)</p>
<p>&#47;&#47; namespace registrieren</p>
<p>$xml->registerXPathNamespace(&ldquo;gut&rdquo;, $namespaces['www.superhelden.com&#47;fraktion&#47;gut']);</p>
<p>&#47;&#47; gib mir alle helden im namespace gut</p>
<p>$heroes = $xml->xpath(&rsquo;&#47;&#47;gut:helden&rsquo;);</p>
<p><&#47;pre></p>
<p>So, das wars auch. Eventuell hilft das ja jemanden weiter. Ich hab wirklich lange gebraucht um darauf zu kommen, dass XPath zu bl&ouml;d daf&uuml;r ist.</p>
