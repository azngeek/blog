---
layout: post
status: publish
published: true
title: Xdebug in Zend Studio for Eclipse freischalten
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 87
wordpress_url: http://blog.azngeek.de/?p=87
date: !binary |-
  MjAwOC0xMi0wNSAwMDo0NzowOCArMDEwMA==
date_gmt: !binary |-
  MjAwOC0xMi0wNCAyMjo0NzowOCArMDEwMA==
categories:
- php
- Entwicklung
tags:
- php
- Add new tag
- Apache HTTP Server
- Development Tools
- Programming
- Integrated development environment
- Open source
- Zend Studio
comments: []
---
<div class="zemanta-img">
<div>
<dl class="wp-caption alignright" style="margin: 1em; float: right; display: block; width: 181px;">
<dt class="wp-caption-dt"><a href="http:&#47;&#47;www.flickr.com&#47;photos&#47;84122371@N00&#47;1716642342"><img title="zend_studio" src="http:&#47;&#47;farm3.static.flickr.com&#47;2254&#47;1716642342_81d2d7eee9_m.jpg" alt="zend_studio" width="171" height="240" &#47;><&#47;a><&#47;dt>
<dd class="wp-caption-dd zemanta-img-attribution" style="font-size: 0.8em;">Image by <a href="http:&#47;&#47;www.flickr.com&#47;photos&#47;84122371@N00&#47;1716642342">CalEvans<&#47;a> via Flickr<&#47;dd><&#47;dl><&#47;div><br />
<&#47;div><br />
Xdebug ist eine m&auml;chtige Erweiterung f&uuml;r den <a class="zem_slink" title="Apache HTTP Server" rel="homepage" href="http:&#47;&#47;httpd.apache.org&#47;">Apache Webserver<&#47;a>. Es handelt sich im Grunde genommen um einen Profiler und Debugger f&uuml;r <a class="zem_slink" title="PHP" rel="homepage" href="http:&#47;&#47;php.net&#47;">PHP<&#47;a> Skripte. Mit Xdebug lassen sich so tolle Sachen machen wie zum Beispiel den kompletten Stacktrace einer Anwendung auszugeben bzw. eine Anwendung zu profilen. Dennoch ist das Alltagswerkzeug vieler Programmierer wohl immer noch var_dump(), print_r(), exit() oder die(). Nicht, dass dies schlecht w&auml;re, aber heutzutage kosten Tools f&uuml;r die professionelle Softwareentwicklung nicht unbedingt viel Geld, besonders nicht wenn es sich dabei um <a class="zem_slink" title="Open source" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Open_source">Open Source<&#47;a> Programme handelt.</p>
<p>Xdebug geh&ouml;rt in dieser Kategorie, frei verf&uuml;gbarer Software. <a class="zem_slink" title="Zend Studio" rel="homepage" href="http:&#47;&#47;www.zend.com&#47;en&#47;products&#47;studio">Zend Studio for Eclipse<&#47;a> nicht. Ich m&ouml;chte jetzt nicht anfangen &uuml;ber Vor- und Nachteile der verschiedenen <a class="zem_slink" title="Integrated development environment" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Integrated_development_environment">IDE<&#47;a> zu reden. Jede IDE hat ihre Daseinsberechtigung. Was im Zend Studio for Eclipse wirklich elegant gel&ouml;st ist, ist der intergrierter Debugger bzw. der Debuggingclient. F&uuml;r alle, die es noch nicht wissen: Zend Studio hat einen Client, der &uuml;beraus komfortabel Remote <a class="zem_slink" title="Debugging" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Debugging">Debugging<&#47;a> erlaubt. Es gibt hier aber leider einen Haken. Das Debugging funktioniert leider nur mit dem ebenfalls von Zend vertriebenen Zend Debugger, der wiederum Teil von Zend Platform ist. Letztere ist kostenpflichtig w&auml;hrend der Debugger weiterhin frei verf&uuml;gbar ist.</p>
<p>W&auml;rend ich also mit Zend Studio for Eclipse arbeite und mir mal die Zeit nehme, die Debuggingfeatures auszuprobieren, f&auml;llt mir eben auf, dass XDebug nicht unterst&uuml;tzt wird. Also mal schnell im Internet geforscht und "Aha", dieses Feature existiert bereits, wird aber nicht offiziell unterst&uuml;zt. Ohne gro&szlig; dar&uuml;ber spekulieren zu m&uuml;ssen, Xdebug hat die besseren Features, ist kostenlos, leicht verf&uuml;gbar und sogar &uuml;ber <a class="zem_slink" title="Positive emitter-coupled logic" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Positive_emitter-coupled_logic">PECL<&#47;a> installierbar und das scheint wohl nicht jedem zu gefallen. Also ohne weiteres gro&szlig;es Tralala, hier die hoffentlich idiotensichere Anleitung zur Installation von xdebug unter Ubunutu Linux und das Freischalten der versteckten Option unter Zend Studio.</p>
<p>Terminal &ouml;ffnen und folgendes eingeben</p>
<pre lang="BASH">sudo apt-get install php5-dev php-pear<&#47;pre><br />
Danach mittels PECL xdebug installieren</p>
<pre lang="BASH">sudo pecl install xdebug<&#47;pre><br />
Nach abgeschlossener Installation sollte PECL so was &Auml;hnliches wie das hier zur&uuml;ckgeben.</p>
<pre lang="BASH">~ > sudo pecl install xdebug<br />
Password:<br />
downloading xdebug-2.0.3.tgz ...<br />
Starting to download xdebug-2.0.3.tgz (286,325 bytes)<br />
......................................................done: 286,325 bytes<br />
...<br />
Build process completed successfully<br />
Installing '&#47;usr&#47;lib&#47;php&#47;extensions&#47;no-debug-non-zts-20060613&#47;xdebug.so'<br />
install ok: channel:&#47;&#47;pecl.php.net&#47;xdebug-2.0.3<br />
configuration option "php_ini" is not set to php.ini location<br />
You should add "extension=xdebug.so" to php.ini<&#47;pre><br />
Hier steht also dass wir die Erweiterung xdebug in die php.ini einf&uuml;gen sollen. Netterweise liefert die Meldung auch gleich den kompletten richtigen Pfad mit. Unter <a class="zem_slink" title="Ubuntu" rel="homepage" href="http:&#47;&#47;www.ubuntu.com&#47;">Ubuntu<&#47;a> funktioniert das so:</p>
<pre lang="BASH">sudo gedit &#47;etc&#47;php5&#47;apache2&#47;php.ini<&#47;pre><br />
Nun nur noch folgende Zeile irgendwo in die php.ini einf&uuml;gen</p>
<pre lang="INI">[xdebug]<br />
extension=xdebug.so<&#47;pre><br />
Jetzt muss der Apache nur noch neu gestartet werden und xdebug ist aktiviert.</p>
<pre lang="BASH">[xdebug]<br />
sudo &#47;etc&#47;init.d&#47;apache2 reload<&#47;pre><br />
Um den xdebug Support f&uuml;r Zend Studio for Eclipse freizuschalten muss folgendes gemacht werden.</p>
<pre lang="BASH">#Falls die IDE dort liegt<br />
cd &#47;usr&#47;local&#47;ZendStudio&#47;plugins<br />
#einen neuen Order 'disabled' anlegen<br />
Alle Dateien mit dem Prefix com.zend.php.debug* ins disabled Verzeichnis kopieren<br />
mv com.zend.php.debug* disabled<br />
#Zend Studio neu starten<br />
.&#47;ZendStudio -clean<&#47;pre><br />
Innerhalb von Zend Studio lassen sich nun &uuml;ber das Debuggingmen&uuml; die xdebug Erweiterung einschalten.</p>
<p>Fazit</p>
<p>xdebug ist in den richtigen H&auml;nden ein sehr m&auml;chtiges Tool zur Analyse und Debugging von Anwendungen. Leider fehlt mir die Zeit, einen umfassenden Artikel &uuml;ber xdebug zu schreiben und ehrlich gesagt mache ich das Profilen haupts&auml;chlich &uuml;ber die Konsole und das Debuggen mit PHP internen Funktionen. Eventuell liegt es auch daran, dass Debuggingfunktionalit&auml;ten oft nicht out of the box verf&uuml;gbar sind. Zumindest bei einer kommerziellen IDE wie Zend Studio for Eclipse sollte dies der Fall sein. Dass dies nun mal nicht unbedingt so ist und dass es dennoch geht habe ich ja mit diesen Artikel bewiesen.</p>
<h6 class="zemanta-related-title" style="font-size: 1em;">Related articles by Zemanta<&#47;h6></p>
<ul class="zemanta-article-ul">
<li class="zemanta-article-ul-li"><a href="http:&#47;&#47;www.articlesbase.com&#47;article.php?aid=626396&amp;pid=6775764102">5 Easy Tips for Faster Php Development<&#47;a><&#47;li>
<li class="zemanta-article-ul-li"><a href="http:&#47;&#47;www.smashingmagazine.com&#47;2009&#47;01&#47;20&#47;50-extremely-useful-php-tools&#47;">50 Extremely Useful PHP Tools<&#47;a><&#47;li><br />
<&#47;ul></p>
<div class="zemanta-pixie" style="margin-top: 10px; height: 15px;"><a class="zemanta-pixie-a" title="Zemified by Zemanta" href="http:&#47;&#47;reblog.zemanta.com&#47;zemified&#47;33af90e5-f3e8-49c6-b8f2-16dd09086ec2&#47;"><img class="zemanta-pixie-img" style="border: medium none; float: right;" src="http:&#47;&#47;img.zemanta.com&#47;reblog_e.png?x-id=33af90e5-f3e8-49c6-b8f2-16dd09086ec2" alt="Reblog this post [with Zemanta]" &#47;><&#47;a><&#47;div></p>
