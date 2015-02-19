---
layout: post
status: publish
published: true
title: Skype unter Ubuntu installieren
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: Skype unter Ubuntu installieren. Mit Medibuntu gehts - und das sogar ziemlich
  simpel. Ein Quickturial findet ihr hier.
wordpress_id: 119
wordpress_url: http://blog.azngeek.de/?p=119
date: !binary |-
  MjAwOC0xMi0xOSAxMzo1ODozOSArMDEwMA==
date_gmt: !binary |-
  MjAwOC0xMi0xOSAxMTo1ODozOSArMDEwMA==
categories:
- Administration
- Tutorial
tags:
- skype
- ubuntu
- medibuntu
- Advanced Packaging Tool
- Sudo
- Linux
- Outlook
- Operating system
- Add new tag
comments:
- id: 1119
  author: KDK
  author_email: bukdk@gmx.de
  author_url: ''
  date: !binary |-
    MjAwOS0wMS0wOCAyMTo1Nzo0MyArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMS0wOCAxOTo1Nzo0MyArMDEwMA==
  content: ! "Zum besseren Verst&auml;ndnis ( musste einiges ausprobieren ) sollte
    man vermerken, dass es es bei -O um den Buchstaben und bei &amp;&amp; um ein doppeltes
    Ampersand-Zeichen ( Zeichen &uuml;ber der Taste 6 ) handelt.\r\n\r\nWenn man Ubuntu-Anf&auml;nger
    ( wie ich ) ist und von HTML keine Ahnung hat ( die hatte ich zum Gl&uuml;ck ),
    dann kommt man schnell in eine Sackgasse.\r\n\r\nKDK"
- id: 1843
  author: Klaus Friese
  author_email: klaus_friese@yahoo.de
  author_url: ''
  date: !binary |-
    MjAxMi0xMS0xNiAyMDowNzowNiArMDEwMA==
  date_gmt: !binary |-
    MjAxMi0xMS0xNiAxOTowNzowNiArMDEwMA==
  content: ! "Hallo DonBosco,\r\n\r\nvielen Dank f&uuml;r Deine informative Seite:\r\nhttp:&#47;&#47;www.azngeek.de&#47;administration&#47;skype-unter-ubuntu-installieren\r\n\r\nLeider
    habe ich es aber nicht geschafft, Skype unter Ubuntu 12.04.1 zu installieren.
    Die Zeile :\r\ndo aptitude install skype\r\nist wohl fehlerhaft. Deshalb habe
    ich versucht, sie ver&auml;ndert einzugeben:\r\nsudo aptitude install skype\r\n\r\nAber
    Skype wird trotzdem nicht gefunden.\r\n\r\nKannst Du mir hier helfen?\r\n\r\nUnd,
    - falls das nicht klappt, kann man die &Auml;nderungen, die ich durch folgende
    Zeilen in mein System geholt habe, wieder r&uuml;ckg&auml;ngig machen?\r\n\r\n\r\nsudo
    wget -q http:&#47;&#47;packages.medibuntu.org&#47;medibuntu-key.gpg -O- | sudo
    apt-key add - &amp;&amp; sudo apt-get update\r\n\r\nwget -q http:&#47;&#47;packages.medibuntu.org&#47;medibuntu-key.gpg
    -O- | sudo apt-key add - &amp;&amp; sudo apt-get update\r\n\r\nF&uuml;r eine Antwort
    w&auml;re ich sehr dankbar.\r\n\r\nHerzliche Gr&uuml;&szlig;e\r\n\r\nKlaus Friese,
    Hamburg"
---
<p>So, mein System hat es mal wieder zerschossen. Nicht wirklich ohne dass ich nichts getan h&auml;tte :)</p>
<div class="zemanta-img zemanta-action-dragged">
<div>
<dl class="wp-caption alignright" style="margin: 1em; float: right; display: block; width: 212px;">
<dt class="wp-caption-dt"><a href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Image:Skype_logo2.svg"><img title="Skype Limited" src="http:&#47;&#47;upload.wikimedia.org&#47;wikipedia&#47;en&#47;thumb&#47;6&#47;65&#47;Skype_logo2.svg&#47;202px-Skype_logo2.svg.png" alt="Skype Limited" width="202" height="89" &#47;><&#47;a><&#47;dt>
<dd class="wp-caption-dd zemanta-img-attribution" style="font-size: 0.8em;">Image via <a href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Image:Skype_logo2.svg">Wikipedia<&#47;a><&#47;dd> <&#47;dl><&#47;div><br />
<&#47;div><br />
Wie auch immer, mein Kommunikationsmittel der Wahl abseits von <a class="zem_slink" title="Outlook (magazine)" rel="wikipedia" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Outlook_%28magazine%29">Outlook<&#47;a> ist nat&uuml;rlich <a class="zem_slink" title="Skype" rel="homepage" href="http:&#47;&#47;www.skype.com&#47;">Skype<&#47;a>. Leider gibt es unter <a class="zem_slink" title="Ubuntu" rel="homepage" href="http:&#47;&#47;www.ubuntu.com&#47;">Ubuntu<&#47;a> Probleme Skype zu installieren, nicht dass dies so schwer w&auml;re, nein es gibt da lizenzrechtliche Gr&uuml;nde daf&uuml;r.</p>
<blockquote><p>Aufgrund unterschiedlicher Rechtsverhalten in verschiedenen L&auml;ndern ist manche Software nicht in den allgemeinen Ubuntu-Quellen enthalten. Beispielsweise gelten in den Vereinigten Staaten Software-Patente, die in vielen anderen L&auml;ndern nicht gelten. Um Ubuntu-Nutzer zu bef&auml;higen, dort, wo es legal ist, solche Software zu installieren , wurde eine eigene Paketquelle geschaffen<&#47;blockquote><br />
Wie erfahrene Ubuntu- bzw. Debianbenutzer wissen, lassen sich &uuml;ber die Paketverwaltung ganz bequem Anwendungen installieren.</p>
<pre lang="bash">donbosco@desktop:# sudo <a class="zem_slink" title="Advanced Packaging Tool" rel="homepage" href="http:&#47;&#47;wiki.debian.org&#47;Apt">apt-get<&#47;a> install skype<&#47;pre><br />
Nat&uuml;rlich wird dies bei einer Out-Of-The-Box Installation nicht gehen weil Ubuntu dieses Paket in keinem entsprechenden Repositorie findet. N&uuml;tzlicherweise wird abseits der offiziellen Paketquellen noch ein weiteres Projekt seitens der Community betreut. Das Projekt nennt sich <a class="zem_slink" title="Medibuntu" rel="homepage" href="http:&#47;&#47;www.medibuntu.org&#47;">Medibuntu<&#47;a> und es handelt sich dabei im Grunde genommen um ein Repositorie f&uuml;r freie und unfreie Software aus dem Bereich Unterhaltung und Multimedia. Tja, da l&auml;sst sich doch sicherlich auch das geliebte Skype wiederfinden. Doch zuerst m&uuml;ssen die neuen inoffiziellen Paketquellen zur Paketverwaltung hinzugef&uuml;gt werden. Klingt alles kompliziert, ist aber ein Kinderspiel. Einfach folgende Befehle in das Terminal einf&uuml;gen.</p>
<p>Aktuelle Listen ziehen</p>
<pre lang="bash">donbosco@desktop:# sudo wget http:&#47;&#47;www.medibuntu.org&#47;sources.list.d&#47;feisty.list -O &#47;etc&#47;apt&#47;sources.list.d&#47;medibuntu.list<&#47;pre><br />
Paketliste zertifizieren und updaten</p>
<pre lang="bash">wget -q http:&#47;&#47;packages.medibuntu.org&#47;medibuntu-key.gpg -O- | sudo apt-key add - && sudo apt-get update<&#47;pre><br />
Skype installieren</p>
<pre lang="bash">do aptitude install skype<&#47;pre><br />
So, das wars. Skype sollte nun im Anwendungsreiter verf&uuml;gbar sein. Sollte euch der Beitrag irgendwie geholfen haben oder ihr Verbesserungsvorschl&auml;ge habt, bin ich nat&uuml;rlich &uuml;ber jeden Kommentar dankbar.</p>
<div class="zemanta-pixie" style="margin-top: 10px; height: 15px;"><a class="zemanta-pixie-a" title="Zemified by Zemanta" href="http:&#47;&#47;reblog.zemanta.com&#47;zemified&#47;13e6ae79-2c4f-4558-b2f0-459dbba97ab3&#47;"><img class="zemanta-pixie-img" style="border: medium none; float: right;" src="http:&#47;&#47;img.zemanta.com&#47;reblog_e.png?x-id=13e6ae79-2c4f-4558-b2f0-459dbba97ab3" alt="Reblog this post [with Zemanta]" &#47;><&#47;a><&#47;div></p>
