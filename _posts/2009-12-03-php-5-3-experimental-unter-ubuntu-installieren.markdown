---
layout: post
status: publish
published: true
title: PHP 5.3 Experimental unter Ubuntu installieren
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 243
wordpress_url: http://www.azngeek.de/?p=243
date: !binary |-
  MjAwOS0xMi0wMyAxMTo1MTozNiArMDEwMA==
date_gmt: !binary |-
  MjAwOS0xMi0wMyAxMDo1MTozNiArMDEwMA==
categories:
- php
- Administration
tags: []
comments: []
---
<h1>Warum noch eine weitere Anleitung um PHP 5.3 zu installieren?<&#47;h1><br />
Weil es meiner Meinung nach nur wenige Anleitungen gibt die sich mit einem Experimental Build besch&auml;ftigen. Die meisten Anleitungen beschr&auml;nken sich auf Backports und weitere Kleinigkeiten. Das Problem ist dann aber dass Sachen wie PEAR oder PECL einfach nicht mehr funktionieren. Der etwas komplizierterer Weg &uuml;ber einen Experimental Build ist in dem Fall eine erw&auml;hnenswerte Alternative die ich auch hier erkl&auml;ren werde.</p>
<p>Ein Experimental Build ist nicht Anderes als eine&nbsp; Ansamlungen von Quellcode dass vorkonfiguriert verf&uuml;gbar ist aber aufgrund verschiedener Gr&uuml;nde nicht f&uuml;r den Produktiveinsatz freigegeben ist. Dies kann mehrere Ursachen haben. Meistens ist die QA des Debian Projektes wieder mal mit anderen Sachen besch&auml;ftigt. Vergleichen wir die aktuelle Debian Distribution mit der aktuellsten Ubuntu, so sind in Sachen Aktualit&auml;t doch massive Unterschiede. Wer also die aktuellsten Pakete haben m&ouml;chte, muss entweder auf Backports zur&uuml;ckgreifen oder kompilliert sich selber die passenden. Dieser Artikel geht auf das Kompillieren eines Experimental Builds ein und da Ubuntu ja auf Debian basiert sollte das fertige Paket auch problemlos zu installieren sein.</p>
<h2>Vorbereitung<&#47;h2><br />
Da die Installation komplett unter einer Konsole geschieht, sind grundlegende Kentnisse der Shell notwendig. Die Installation wurde auf einem jungfr&auml;ulichen System gemacht um alle Eventualit&auml;ten auszuschlie&szlig;en. Ich empfehle stark das Verwenden einer virtuellen Maschine wie VirtualBox, VmWare oder &Auml;hnliche. In dem Fall verwende ich als Gastsystem Ubuntu 9.04 und als Host einen Hyper-V.</p>
<p>Update (3. Dezember 2009): Ich hab es gerade eben auf Ubuntu 9.10 installiert. Geht ohne Probleme :)</p>
<p>W&auml;hrend des Kompillieren k&ouml;nnt ihr &uuml;brigens ruhig mal f&uuml;r ein paar Stunden an die frische Luft gehen. Bei mir hat es circa zwei Stunden gedauert. Erw&auml;hnenswert ist eventuell noch folgendes Zitat:</p>
<blockquote><p>Never touch a running system!<&#47;blockquote><br />
Auf gut Deutsch: Nicht unbedingt auf einem Produktivserver installieren, besonders nicht wenn euer Job davon abh&auml;ngt. Der Titel sagt es ganz deutlich: Wir bauen uns ein Experimental Build.</p>
<h2>Installation<&#47;h2><br />
Zuerst sollte man sich das Paket installieren dass notwendig ist damit wir Debian Pakete bauen k&ouml;nnen. Versierte Admins w&uuml;rden behaupten es geht auch ohne aber man muss sich das Leben ja nicht schwerer machen. Nebenbei halten wir das System auch auf den aktuellsten Stand.</p>
<pre lang="BASH">sudo apt-get update<br />
sudo apt-get upgrade<br />
sudo apt-get install build-essential<&#47;pre><br />
Nachdem das erledigt ist m&uuml;ssen alle Pakete gezogen werden die nachher beim Kompillieren notwendig sind um potentielle Konflikte zu l&ouml;sen. In dem Fall wollen wir nachher ein PHP5 Build erstellen und m&uuml;ssen daf&uuml;r die Abh&auml;ngigkeiten l&ouml;sen. Das geht ganz einfach mit</p>
<pre lang="BASH">sudo apt-get build-dep php5<&#47;pre><br />
Ich hoffe ihr habt euch inzwischen nen neuen Kaffee gezogen denn solange hat es bei mir gedauert bis alle Pakete drauf waren. Jetzt gehts an die Wurst. Debian listet auf seiner Webseite immer die aktuellsten Pakete auf inklusive den passenden Downloadlink. &Uuml;bersichtshalber findet ihr f&uuml;r PHP 5.3 den Link unter <a title="http:&#47;&#47;packages.debian.org&#47;de&#47;source&#47;experimental&#47;php5" href="http:&#47;&#47;packages.debian.org&#47;de&#47;source&#47;experimental&#47;php5" target="_blank">http:&#47;&#47;packages.debian.org&#47;de&#47;source&#47;experimental&#47;php5<&#47;a>. Aber eigentlich l&auml;sst sich dieser Schritt komplett &uuml;berspringen. Also zieht man sich jetzt einfach den kompletten Quellcode, patcht ihn und sto&szlig;en den Compiler an.</p>
<pre lang="BASH">sudo -s<br />
mkdir -p &#47;source&#47;php<br />
cd &#47;source&#47;php<br />
wget http:&#47;&#47;ftp.de.debian.org&#47;debian&#47;pool&#47;main&#47;p&#47;php5&#47;php5_5.3.0.orig.tar.gz<br />
wget http:&#47;&#47;ftp.de.debian.org&#47;debian&#47;pool&#47;main&#47;p&#47;php5&#47;php5_5.3.0-3.diff.gz<br />
wget http:&#47;&#47;ftp.de.debian.org&#47;debian&#47;pool&#47;main&#47;p&#47;php5&#47;php5_5.3.0-3.dsc<br />
tar -xvzf php5_5.3.0.orig.tar.gz<br />
mv php-5.3.0 php5-5.3.0<br />
cat php5_5.3.0-3.diff.gz |gunzip |patch -p0<br />
cd php5-5.3.0<br />
chmod +x debian&#47;rules<br />
dpkg-buildpackage -us -uc<br />
apt-get install firebird2.0-dev libc-client-dev libmcrypt-dev libmysqlclient15-dev<&#47;pre><br />
Puhh, wenn es hier Probleme gibt k&ouml;nnt ihr das mal posten. M&ouml;glicherweise kann ich da helfen oder ein anderer hilfsbereiter User. Im Idealfall ist das Ding ohne Probleme durchgelaufen und die Pakete lassen sich ganz bequem mit dem Paketmanager installieren.</p>
<pre lang="BASH">sudo dpkg -i *.deb<&#47;pre><br />
Jetzt m&uuml;sste der Paketmanager wegen ungel&ouml;ste Abh&auml;ngigkeit herummeckern also l&ouml;sen wir die mal mit</p>
<pre lang="BASH">sudo apt-get install -f<&#47;pre><br />
Nun noch schnell einen Test im Browser machen nachdem wir Apache neu gestartet haben. Jetzt kr&auml;ftig auf die eigene Schulter klopfen oder dem PC mal ne Pause g&ouml;nnen :P</p>
<pre lang="BASH">sudo &#47;etc&#47;init.d&#47;apache2 restart<&#47;pre><br />
[caption id="attachment_259" align="alignnone" width="520" caption="phpinfo mit php 5.3"]<img class="size-full wp-image-259   " title="phpinfo" src="http:&#47;&#47;www.azngeek.de&#47;wp-content&#47;uploads&#47;2009&#47;12&#47;phpinfo.jpg" alt="phpinfo mit php 5.3" width="520" height="320" &#47;>[&#47;caption]</p>
<p>So, das wars. Bei Anregungen zu dem Artikel oder Kritik oder einfach nur weil ihr Danke sagen wollts, k&ouml;nnt ihr mir gerne einen Kommentar hinterlassen.</p>
