---
layout: post
status: publish
published: true
title: Mit SSH auf das IPhone verbinden
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 162
wordpress_url: http://blog.azngeek.de/?p=162
date: !binary |-
  MjAwOS0wMS0yNyAxNzozNzo0MCArMDEwMA==
date_gmt: !binary |-
  MjAwOS0wMS0yNyAxNTozNzo0MCArMDEwMA==
categories:
- Geek Stuff
- Apache
tags:
- Add new tag
- Apple
- IPhone
- Cydia
- OpenSSH
comments: []
---
<p>Bereits seit L&auml;ngerem ist es m&ouml;glich, sein IPhone zu cracken bzw. sagen wir mal lieber jailbreaken wie es ja neuerdings genannt wird. Was sich so tolles mit einem gecrackten IPhone anstellen l&auml;sst findet der interessierte Nutzer in unz&auml;hligen Quellen. Eine simple Suche bei Google sollte die meisten Fragen beantworten.</p>
<p>Von mir hierzu nur ein Quote, gefunden bei maclife.de</p>
<blockquote><p>Unter dem Begriff "Jailbreak" wird im Zusammenhang mit dem <a class="zem_slink" title="iPhone" rel="homepage" href="http:&#47;&#47;www.apple.com&#47;iphone">iPhone<&#47;a> das Freischalten des Ger&auml;tes f&uuml;r die Installation von Drittanbieter-Software verstanden. Der allgegenw&auml;rtige iPhone Atlas hat nun noch einmal eine komplette &Uuml;bersicht ver&ouml;ffentlicht, die das Vorgehen unter verschiedenen Firmware-Versionen des iPhone beschreibt. Alle Vorgehensweisen sollen zu dem gleichen Ergebnis f&uuml;hren: der M&ouml;glichkeit, Daten in das Dateisystem des iPhone zu schreiben und der Installation von installer.app, zum Katalogisieren von iPhone-Applikationen.<&#47;blockquote><br />
Eine nette Spielerei, insbesondere f&uuml;r den Alltag als <a class="zem_slink" title="Linux" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Linux">Linux<&#47;a>&#47;Unixanwender ist der Remotezugriff auf das IPhone &uuml;ber SSH. Nicht nur, dass danach viele vertraute <a class="zem_slink" title="Unix" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Unix">UNIX<&#47;a> Befehle zur Verf&uuml;gung stehen, nein es ist tats&auml;chlich sogar m&ouml;glich, &uuml;ber den aufgebauten SSH Tunnel, eine Internetverbindung aufzubauen. Zugegebenerma&szlig;en ein ziemlicher Overkill nur um ins Internet zu kommen aber der Versuch alleine ist es wert.</p>
<p><strong>1. <a class="zem_slink" title="OpenSSH" rel="homepage" href="http:&#47;&#47;www.openssh.com">OpenSSH<&#47;a> installieren<&#47;strong></p>
<p>Damit eine Remoteverbindung aufgebaut wird, installiert man &uuml;ber das gecrackte IPhone mittels Cydia daie Pakete <a class="zem_slink" title="Berkeley Software Distribution" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Berkeley_Software_Distribution">BSD<&#47;a> Subsystem, Community Sources und OpenSSH. Die</p>
<div class="zemanta-img zemanta-action-dragged">
<div>
<dl class="wp-caption alignright" style="margin: 1em; float: right; display: block; width: 204px;">
<dt class="wp-caption-dt"><a href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Image:OpenSSH_logo.png"><img title="OpenSSH" src="http:&#47;&#47;upload.wikimedia.org&#47;wikipedia&#47;en&#47;6&#47;65&#47;OpenSSH_logo.png" alt="OpenSSH" width="194" height="191" &#47;><&#47;a><&#47;dt>
<dd class="wp-caption-dd zemanta-img-attribution" style="font-size: 0.8em;">Image via <a href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Image:OpenSSH_logo.png">Wikipedia<&#47;a><&#47;dd><&#47;dl><&#47;div><br />
<&#47;div><br />
Installation verl&auml;uft &auml;hnlich wie die Installation eines Paktektes mit Hilfe vom dem bereits aus <a class="zem_slink" title="Debian" rel="homepage" href="http:&#47;&#47;www.debian.org&#47;">Debian<&#47;a> bekannten APT. Cydia versteht sich also als grafisches Frontend f&uuml;r die Paketverwaltung.</p>
<p>OpenSSH installiert einen SSH-Server auf dem IPhone und erlaubt es, sich remote auf das IPhone zu verbinden.</p>
<p>BSD Subsystem stellt den User auf dem IPhone eine Vielzahl an Anwendungen bereit, die Zugriff und Manipulation direkt auf dem IPhone via Kommandozeilentools erlauben.</p>
<p><strong>2. SSH verbindung aufbauen<&#47;strong></p>
<p>Um die SSH Verbindung aufzubauen, muss erstmal die IP vom IPhone herausgefunden werden. Ich benutze SBPrefs um sie mir anzuzeigen, alle Anderen k&ouml;nnen ja die IP aus den Settings ablesen. Jetzt muss openssh nur noch auf dem Iphone aktiviert werden. Auch das mache ich bequem mit SBPrefs und schon kann man sich bequem remote auf das IPhone einloggen.</p>
<pre lang="bash">#einloggen als root auf das iphone<br />
#ssh root@IPADRESSE<br />
ssh root@192.168.0.53<br />
#das default passwort 'alpine' eingeben<br />
password:alpine<&#47;pre><br />
<strong>3. Und nun?<&#47;strong></p>
<p>Ja wer diese Frage selber nicht beantworten kann sollte sich schnellstm&ouml;glich wieder ausloggen, denn ihr befindet euch mit root-Rechten auf dem IPhone. Und damit l&auml;sst sich nicht nur allerhand tolles Zeug anstellen sondern auch ziemlich viel kaputt machen, alle Anderen k&ouml;nnen nun zum Beispiel:</p>
<p><strong>4. Unixbefehle ausprobieren<&#47;strong></p>
<p>Da das IPhone auf OSX basiert und OSX wiederum auf Darwin und Darwin ein UNIX Derivat ist, lassen sich auch zumindest die &uuml;blichen UNIX&#47;Linux Befehle ausf&uuml;hren.</p>
<pre lang="bash">#cd um verzeichne zu wechseln<br />
cd &#47;private<br />
#clear um den bildschirm zu leeren<br />
clear<br />
#df um aktuellen speicherverbrauch auf der platte anzuzeigen<br />
df<br />
#ls um dateien und verzeichnisse aufzulisten<br />
ls -l<&#47;pre><br />
<strong>5. Dateien kopieren<&#47;strong></p>
<p>Den einfachsten Zugriff auf das IPhone bekommt man mit einem <a class="zem_slink" title="SSH file transfer protocol" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;SSH_file_transfer_protocol">SFTP<&#47;a> Client. Unter <a class="zem_slink" title="Windows" rel="homepage" href="http:&#47;&#47;www.microsoft.com&#47;WINDOWS">Windows<&#47;a> ist das <a class="zem_slink" title="WinSCP" rel="homepage" href="http:&#47;&#47;winscp.net&#47;">WinSCP<&#47;a>, Linux- und Unixbenutzer benutzen einfach eins der mitgelieferten Clients. Ich benutze Nautilus. Es l&auml;sst sich auch dank root-Reche auch ganz bequem Verzeichnisse und Dateien anlegen.</p>
<h6 class="zemanta-related-title" style="font-size: 1em;">Related articles by Zemanta<&#47;h6></p>
<ul class="zemanta-article-ul">
<li class="zemanta-article-ul-li"><a href="http:&#47;&#47;en.onsoftware.com&#47;use-software-to-add-missing-functions-to-your-iphone&#47;">Use software to add missing functions to your iPhone<&#47;a><&#47;li>
<li class="zemanta-article-ul-li"><a href="http:&#47;&#47;ouriel.typepad.com&#47;myblog&#47;2008&#47;12&#47;iphone-22-tweak.html">10 iPhone 2.2 Tweaks and hacks<&#47;a><&#47;li>
<li class="zemanta-article-ul-li"><a href="http:&#47;&#47;lifehacker.com&#47;5121913&#47;yellowsn0w-unlocks-the-iphone-3g-for-some">Yellowsn0w Unlocks the iPhone 3G (for Some) [IPhone]<&#47;a><&#47;li><br />
<&#47;ul></p>
<div class="zemanta-pixie" style="margin-top: 10px; height: 15px;"><a class="zemanta-pixie-a" title="Zemified by Zemanta" href="http:&#47;&#47;reblog.zemanta.com&#47;zemified&#47;d61dc7e5-ea9a-41b3-8eca-c70fc58129d7&#47;"><img class="zemanta-pixie-img" style="border: medium none; float: right;" src="http:&#47;&#47;img.zemanta.com&#47;reblog_e.png?x-id=d61dc7e5-ea9a-41b3-8eca-c70fc58129d7" alt="Reblog this post [with Zemanta]" &#47;><&#47;a><&#47;div></p>
