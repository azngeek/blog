---
layout: post
status: publish
published: true
title: Apache 2, PHP und MySQL unter Ubuntu installieren
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 122
wordpress_url: http://blog.azngeek.de/?p=122
date: !binary |-
  MjAwOC0xMi0yMiAxMzo1NjowNCArMDEwMA==
date_gmt: !binary |-
  MjAwOC0xMi0yMiAxMTo1NjowNCArMDEwMA==
categories:
- php
- mysql
- Administration
- Tutorial
tags:
- php
- apache
- ubuntu
- mysql
- modrewrite
- Sudo
- Linux
- Add new tag
- LAMP
- Apache HTTP Server
- Operating Systems
comments:
- id: 1135
  author: crashkid
  author_email: info@crashsource.de
  author_url: http://crashsource.de
  date: !binary |-
    MjAwOS0wMS0zMSAxMjo0Njo0MCArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMS0zMSAxMDo0Njo0MCArMDEwMA==
  content: ! "Vielen Dank fuer diese Anleitung. Die Installation hat unter Ubuntu
    Intrepid Ibex wunderbar funktioniert.\r\n\r\nZusaetzlich koenntest du noch die
    Installation von phpmyadmin mittels <em>sudo apt-get install phpmyadmin<&#47;em>
    und die Konfiguration fuer den Apache2-Server beschreiben. Sonderlich schwierig
    ist das zwar nicht, aber ese wuerde deine Anleitung meiner Meinung nach vervollstaendigen.
    ;)"
- id: 1137
  author: donbosco
  author_email: donbosco.rulz@gmail.com
  author_url: http://www.azngeek.de
  date: !binary |-
    MjAwOS0wMi0wMSAwMjo0MDo1NSArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMi0wMSAwMDo0MDo1NSArMDEwMA==
  content: ! 'Hi,

    vielen Dank f&uuml;r dein Feedback. Ich habe bis jetzt noch nie PHPMyAdmin pet
    Paketmanagemen installiert weil ich es doch lieber direkt von SourceForge runterlade.
    Aber der vollst&auml;ndigkeit halber werde ich es mal hinzuf&uuml;gen, nat&uuml;rlich
    erst, nachdem ich die Installation getestet habe :)


    Bez&uuml;glich Apache 2 Konfiguration, die ist gar nicht so einfach, zumindest
    wenn man sich mit mehr herumschlagen m&ouml;chte als nur eine Domain. Eventuell
    finde ich ja mal Zeit, Apache 2 Basics runterzuschreiben.'
- id: 1261
  author: knallerbob
  author_email: safdasdf@ddsd.de
  author_url: ''
  date: !binary |-
    MjAwOS0wMy0xOCAyMToxNDozNiArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMy0xOCAxOToxNDozNiArMDEwMA==
  content: ! "Bei mir kommt die Fehlermedulung:\r\nsudo: can&acute;t set runas group
    vector: Operation not permitted ...\r\n\r\nWas tun?!"
- id: 1262
  author: donbosco
  author_email: donbosco.rulz@gmail.com
  author_url: http://www.azngeek.de
  date: !binary |-
    MjAwOS0wMy0xOSAyMTo0MToyMCArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMy0xOSAxOTo0MToyMCArMDEwMA==
  content: Tut mir leid, ich kenne diese Fehlermeldung nicht. Ich hab auch gerade
    danach gegoogelt. Welche Ubuntuversion benutzt du? Versuch es doch mit einer neuen,
    frischen Installation. Danach sollte es eigentlich gehen.
- id: 1273
  author: Markus
  author_email: keine@domain.at
  author_url: ''
  date: !binary |-
    MjAwOS0wOC0xOCAwOToyMDo1NiArMDIwMA==
  date_gmt: !binary |-
    MjAwOS0wOC0xOCAwNzoyMDo1NiArMDIwMA==
  content: Sehr gutes Tut - Danke! :)
- id: 1305
  author: luigi
  author_email: luigi271@web.de
  author_url: ''
  date: !binary |-
    MjAwOS0xMi0xNiAyMjo1NDoyNiArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0xMi0xNiAyMTo1NDoyNiArMDEwMA==
  content: hallo kann mir jemand helfen und sagen welche ports mann f&uuml;r filezilla
    freigen mu&szlig; ich nutze ubuntu 9.10 danke
- id: 1331
  author: J&ouml;rg
  author_email: dog_jpwhfhymgy@kurzepost.de
  author_url: ''
  date: !binary |-
    MjAxMC0wMS0yMiAxNjoyODo1MyArMDEwMA==
  date_gmt: !binary |-
    MjAxMC0wMS0yMiAxNToyODo1MyArMDEwMA==
  content: ! "Danke f&uuml;r die tolle Anleitung! Hat unter (K)Ubuntu 9.10 einwandfrei
    geklappt.\r\n\r\nVielleicht solltest Du noch ein Wort zu dem var&#47;www - Verzeichnis
    sagen, dass im lokalen Betrieb nicht beschreibbar ist\r\nUnd vielleicht ein Wort,
    wie das DocumentRoot-Verzeichnis ge&auml;ndert werden kann."
- id: 1337
  author: admin
  author_email: donbosco.rulz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMC0wMy0xNiAxNToyNjo1MSArMDEwMA==
  date_gmt: !binary |-
    MjAxMC0wMy0xNiAxNDoyNjo1MSArMDEwMA==
  content: Danke f&uuml;r das nette Kompliment. Ich werde das Tutorial auch in Zukunft
    weiter pflegen und bin f&uuml;r jeden Hinweis sehr dankbar.
- id: 1348
  author: Sun
  author_email: PsychoticInsane@googlemail.com
  author_url: ''
  date: !binary |-
    MjAxMC0wNC0yMyAxNDo1OToxNCArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0wNC0yMyAxMzo1OToxNCArMDIwMA==
  content: Danke, damit hab sogar ich das als absolut talentfreie Computernutzerin
    und Ubuntu-Neuling hinbekommen!
- id: 1349
  author: Christoph
  author_email: christoph_m@gmx.net
  author_url: ''
  date: !binary |-
    MjAxMC0wNS0xMyAxNDozNzowMCArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0wNS0xMyAxMzozNzowMCArMDIwMA==
  content: Danke f&uuml;r den beschreibenden Text. Habe mich f&uuml;r diese Installationsweise
    entschieden nachdem xampp nicht richtig funktionierte.  Erg&auml;nzend k&ouml;nnte
    man noch beschreiben wie man mysql startet&#47;stoppt und wie man PHP in der Kommandozeile
    nutzt.
- id: 1356
  author: Felix W.
  author_email: felix.wieja@gmx.net
  author_url: ''
  date: !binary |-
    MjAxMC0wOS0yNyAxNzoxNDozOSArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0wOS0yNyAxNjoxNDozOSArMDIwMA==
  content: ! "hi bei mir kommt immer die meldung\r\nconfusius@Confusius-Server:&#47;var&#47;www$
    touch index.php\r\ntouch: kann &bdquo;index.php&ldquo; nicht ber&uuml;hren: Permission
    denied\r\n\r\nwas kann ich dagegen tuhen?\r\nhab die neuste ubuntu version :("
- id: 1357
  author: ejzhik
  author_email: ejzhik@yahoo.de
  author_url: http://lakebaikal.eu
  date: !binary |-
    MjAxMC0wOS0yOSAwNjowMDo0MiArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0wOS0yOSAwNTowMDo0MiArMDIwMA==
  content: ! "Danke f&uuml;r die Anleitung, hab mal wieder neue Festplatten und dank
    deiner \r\nschrittweisen Anleitung funktioniert der Lamp server wieder:-)\r\nNach
    ner gewissen Zeit vergisst man halt gewisse Kleinigkeiten..."
- id: 1360
  author: Mitch
  author_email: rosenbaum.mitch@googlemail.com
  author_url: ''
  date: !binary |-
    MjAxMC0xMC0yOSAxMzo1OToxNyArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0xMC0yOSAxMjo1OToxNyArMDIwMA==
  content: ! "Hi,\r\ngut erkl&auml;rt!! Aber ich m&uuml;sste wissen wie man das Programm
    wieder deinstalliert! Ich w&uuml;rd gerne xampp verwenden, da ich das schon mit
    Vista verwendet habe!\r\nWenn du (mir) das noch schreiben k&ouml;nntest w&auml;rs
    echt wunderbar!!\r\n\r\nGru&szlig; Mitch"
- id: 1361
  author: admin
  author_email: donbosco.rulz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMC0xMC0yOSAxNDowNzo1MSArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0xMC0yOSAxMzowNzo1MSArMDIwMA==
  content: ! "Hallo Mitch, \n\nmit XAMPP meinst du sicher das das Projekt von apachefriends.org.
    Es gibt unter folgender URL <em>http:&#47;&#47;www.apachefriends.org&#47;en&#47;xampp-linux.html<&#47;em>
    eine Anleitung. Ich muss wirklich sagen dass ich das noch nie probiert habe da
    man damit ein St&uuml;ck Kontroller verliert wie ich finde. Viele Sachen braucht
    man eigentlich gar nicht und wenn man sich selber mit der Thematik auseinandersetzt
    so ist es doch viel angenehmer zu wissen, welche Software man wo installiert hat.\n\nDeinstallieren
    kannst du das ganze &uuml;brigens wieder mit \"apt-get remove --purge \". Ersetze
    einfach die Variable  mit der entsprechender Paketbezeichnung. Bei php5 w&auml;re
    der Befehl entsprechend. \n\"apt-get remove --purge php5.\n\nMFG"
- id: 1362
  author: admin
  author_email: donbosco.rulz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMC0xMC0yOSAxNDowODowOCArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0xMC0yOSAxMzowODowOCArMDIwMA==
  content: Gerne geschehen :)
- id: 1363
  author: admin
  author_email: donbosco.rulz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMC0xMC0yOSAxNDowODo0NiArMDIwMA==
  date_gmt: !binary |-
    MjAxMC0xMC0yOSAxMzowODo0NiArMDIwMA==
  content: Es scheint so als ob du ekeine administrativen Rechte hast. Hast du schon
    mal versucht mit sudo Adminrechte zu bekommen?
- id: 1364
  author: Nico
  author_email: nikimmel@web.de
  author_url: http://black-angel.de.to
  date: !binary |-
    MjAxMC0xMS0wMSAxNTo1MjoyOCArMDEwMA==
  date_gmt: !binary |-
    MjAxMC0xMS0wMSAxNDo1MjoyOCArMDEwMA==
  content: ! "Sehr gute anleitung hat mir sehr weitergeholfen. : )\r\n\r\nVieeelen
    Dank.\r\n\r\nMFG Nico"
- id: 1398
  author: Jens
  author_email: jens.etheber@online.de
  author_url: ''
  date: !binary |-
    MjAxMS0wMy0xMCAxMTowMTo1OSArMDEwMA==
  date_gmt: !binary |-
    MjAxMS0wMy0xMCAxMDowMTo1OSArMDEwMA==
  content: ! "Ich habe hier ein Problem:\r\n\r\n# phpinfo in die datei reinschreiben\r\necho
    ' > index.php'\r\n\r\n4. Nun noch ein kleiner Check im Browser um zu &uuml;berpr&uuml;fen,
    dass auch wirklich alles funktioniert hat. Daf&uuml;r einfach folgendes in den
    Browser eingeben:\r\n\r\n# im browser in die adresszeile folgendes eingeben\r\n\r\nhttp:&#47;&#47;localhost&#47;index.php\r\n\r\n5.
    Es sollten nun bei einer erfolgreichen Konfiguration zahlreiche Informationen
    zur bestehenden Installation auftauchen.\r\n\r\nwenn ich meine seite aufrufe steht
    da nur phpinfo aber keine Installationsinformationen, ich habe mich genau an die
    o.a.  Schritte gehalten."
- id: 1399
  author: admin
  author_email: donbosco.rulz@gmail.com
  author_url: ''
  date: !binary |-
    MjAxMS0wMy0xMCAxMToyODoyNCArMDEwMA==
  date_gmt: !binary |-
    MjAxMS0wMy0xMCAxMDoyODoyNCArMDEwMA==
  content: ! 'Hallo Jens,


    habe das Tutorial geupdatet. Es sind scheinbar ein paar Zeichen durch die Datenbankmigration
    verloren gegangen. Richtig ist nat&uuml;rlich:


    echo '' index.php


    Das echo macht nichts Anderes als den String ''<? phpinfo()&#039; in die Datei
    index.php zu schreiben. Alternativ k&ouml;nntest du auch einen Editor deiner Wahl
    benutzen.'
- id: 1521
  author: AischaW
  author_email: knieriem@gmx.de
  author_url: ''
  date: !binary |-
    MjAxMS0wNy0yMCAxNzowMjoyMiArMDIwMA==
  date_gmt: !binary |-
    MjAxMS0wNy0yMCAxNjowMjoyMyArMDIwMA==
  content: Danke f&uuml;r die &uuml;bersichtliche und klare Anleitung.
- id: 1853
  author: Walid
  author_email: office@awad.at
  author_url: http://www.webcommerce.at
  date: !binary |-
    MjAxMi0xMi0wNyAxNDo0ODoyMCArMDEwMA==
  date_gmt: !binary |-
    MjAxMi0xMi0wNyAxMzo0ODoyMCArMDEwMA==
  content: Danke f&uuml;r die gute Anleitung
- id: 1860
  author: php-Anf&auml;nger
  author_email: chris@php-homepage.com
  author_url: http://php-homepage.com/php
  date: !binary |-
    MjAxMy0wMS0xMCAyMjoyNjozNiArMDEwMA==
  date_gmt: !binary |-
    MjAxMy0wMS0xMCAyMToyNjozNiArMDEwMA==
  content: ! "Hallo und Danke\r\nNach jeder neuen Version gibts neue T&uuml;cken Lamp
    zu installieren.\r\nKann endlich wieder mit PHP weitermachen.-)"
- id: 1869
  author: Halil
  author_email: haliltepeciklioglu@googlemail.com
  author_url: ''
  date: !binary |-
    MjAxMy0wMi0yNyAxMzo1MzoxNiArMDEwMA==
  date_gmt: !binary |-
    MjAxMy0wMi0yNyAxMjo1MzoxNiArMDEwMA==
  content: ! "Hallo ich habe apache2 und MySQL instaliert wenn ich im Browser pi der
    Rechner eingebe kommt Meldung it s work.\r\nAlso muss es schon mal richtig instaliert
    sein doch wie muss ich jetzt weitervorgehen damit ich &uuml;ber denn Webbrowser
    auf bestimmte Verzeichnis gelange \r\nMfG"
---
<h1><strong>Apache 2, <a class="zem_slink" title="PHP" href="http:&#47;&#47;php.net&#47;" rel="homepage">PHP<&#47;a> und <a class="zem_slink" title="MySQL" href="http:&#47;&#47;www.mysql.com" rel="homepage">MySQL<&#47;a> unter <a class="zem_slink" title="Ubuntu" href="http:&#47;&#47;www.ubuntu.com&#47;" rel="homepage">Ubuntu<&#47;a> installieren<&#47;strong><&#47;h1></p>
<h2><strong>Buchempfehlungen<&#47;strong><&#47;h2><br />
Das folgende Tutorial bezieht sich auf meine Kenntnisse ich ich im Laufe der Zeit erworben habe. Dabei lerne ich jeden Tag etwas dazu und recherchiere viel, insbesondere aber habe ich die Erfahrung gemacht dass vor Allem B&uuml;cher oftmals viel genauere Informationen beinhalten k&ouml;nnen als die im Internet verf&uuml;gbaren Informationen. Ich habe daher eine kleine Auflistung an B&uuml;cher aufgestellt von denen ich der Meinung bin dass sie wirklich hilfreich im Alltag sind. Solltest du dich f&uuml;r eines der B&uuml;cher interessieren, kannst du gerne auf einen der Bilder dr&uuml;cken und unterst&uuml;tzt mich auch dabei, die Serverkosten niedrig zu halten.</p>
<p><a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3836217651&#47;ref=as_li_tf_il?ie=UTF8&tag=azngeek-21&linkCode=as2&camp=1638&creative=6742&creativeASIN=3836217651"><img border="0" src="http:&#47;&#47;ws.assoc-amazon.de&#47;widgets&#47;q?_encoding=UTF8&Format=_SL160_&ASIN=3836217651&MarketPlace=DE&ID=AsinImage&WS=1&tag=azngeek-21&ServiceVersion=20070822" title="Ubuntu GNU Linux"><&#47;a><img src="http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&l=as2&o=3&a=3836217651" width="1" height="1" border="0" alt="Ubuntu GNU Linux" style="border:none !important; margin:0px !important; float:left !important;" &#47;></p>
<p><a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3836217651&#47;ref=as_li_tf_tl?ie=UTF8&tag=azngeek-21&linkCode=as2&camp=1638&creative=6742&creativeASIN=3836217651"> Fischer<&#47;a><img src="http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&l=as2&o=3&a=3836217651" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" &#47;> liefert einen kurzen Einstieg zu Hintergrund und Grundlagen inklusive Installation und darauf folgend einen sauberen und verst&auml;ndlichen Zugang zu Ubuntu f&uuml;r Einsteiger, der von den Desktop-Umgebungen Unity (die Neue) &uuml;ber GNOME zu KDE und von da bis zu Mail, Office (Libre-Office, der Nachfolger von OpenOffice), Bildbearbeitung und Multimedia verl&auml;uft. Soviel zum Einstieg. Dann folgt das fortgeschrittene Profilager: die Administration und der Servereinsatz. Zuletzt dann Hilfe und Referenz. <&#47;p></p>
<p><a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3827330246&#47;ref=as_li_tf_il?ie=UTF8&tag=azngeek-21&linkCode=as2&camp=1638&creative=6742&creativeASIN=3827330246" title="Ubuntu Server"><img border="0" src="http:&#47;&#47;ws.assoc-amazon.de&#47;widgets&#47;q?_encoding=UTF8&Format=_SL160_&ASIN=3827330246&MarketPlace=DE&ID=AsinImage&WS=1&tag=azngeek-21&ServiceVersion=20070822" ><&#47;a><img src="http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&l=as2&o=3&a=3827330246" width="1" height="1" border="0" alt="Ubuntu Server" style="border:none !important; margin:0px !important; float:left !important;" &#47;></p>
<p>Der Autor geht in seinem Buch <a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3827330246&#47;ref=as_li_tf_tl?ie=UTF8&tag=azngeek-21&linkCode=as2&camp=1638&creative=6742&creativeASIN=3827330246">Ubuntu Server: Installation, Konfiguration, Administration<&#47;a><img src="http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&l=as2&o=3&a=3827330246" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" &#47;></p>
<p> durch den kompletten Aufbau eines Servers, angefangen mit RAID und LVM Einrichtung &uuml;ber Konfiguration des Webservers, FTP Servers, NFS, VPN, Einrichtung als Samba Domaincontroller bis zu einem Backupkapitel (als einziger f&auml;llt der f&uuml;r mein Geschmack etwas d&uuml;rftig aus).</p>
<p>Alle Schritte sind stets verst&auml;ndlich beschrieben und die komplizierten Aufgaben mit Beispielen erl&auml;utert. Beispielsweise erkl&auml;rt Hr. Kofler am Beispiel eines kleinen Heimnetzes die Einrichtung von Samba als Domaincontroller, zusammen mit der entsprechend notwendigen Konfiguration von Linux und Windows Clients. Zus&auml;tzliche Links und Verweise am Ende jedes Kapitels dienen als weitere St&uuml;tze, falls das Buch nicht ausreicht. <&#47;p></p>
<p><a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3827330718&#47;ref=as_li_tf_il?ie=UTF8&tag=azngeek-21&linkCode=as2&camp=1638&creative=6742&creativeASIN=3827330718"><img border="0" src="http:&#47;&#47;ws.assoc-amazon.de&#47;widgets&#47;q?_encoding=UTF8&Format=_SL160_&ASIN=3827330718&MarketPlace=DE&ID=AsinImage&WS=1&tag=azngeek-21&ServiceVersion=20070822" title="Ubuntu 11.4"><&#47;a><img src="http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&l=as2&o=3&a=3827330718" width="1" height="1" border="0" alt="Ubuntu 11.4" style="border:none !important; margin:0px !important; float:left !important;" &#47;></p>
<p>In der 10. Auflage seines beliebten Einsteigerbuchs <a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3827330718&#47;ref=as_li_tf_tl?ie=UTF8&tag=azngeek-21&linkCode=as2&camp=1638&creative=6742&creativeASIN=3827330718">Ubuntu 11.04 "Natty Narwhal"<&#47;a> zeigt Ihnen Linux-Experte Michael Kofler, wie Sie aus Ubuntu 11.04 "Natty Narwhal" und dem neuen Unity-Desktop alles herausholen, was Sie f&uuml;r den PC-Alltag brauchen.</p>
<p>Michael Kofler macht Sie ausf&uuml;hrlich mit Ubuntu vertraut: von der Installation (auch mit WUBI oder VirtualBox unter Windows), &uuml;ber die Konfiguration & Pflege des Systems, die Installation von Programmen, dem Einsatz am Desktop bis hin zur Arbeit im Terminal. Au&szlig;erdem lernen Sie Ubuntus multimediale F&auml;higkeiten kennen (Fotos, Audio, Video). <&#47;p></p>
<h2><strong>Tutorial<&#47;strong><&#47;h2></p>
<p>Eine kleine Anmerkung im Vorfeld: Dieses Tutorial besteht nun bereits seit drei Jahren und ist daher etwas veraltet. Es wird die n&auml;chsten Tage geupdated.</p>
<p>Im folgenden zeige ich, wie man unter Ubuntu sehr schnell einen typischen <a class="zem_slink" title="LAMP (software bundle)" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;LAMP_%28software_bundle%29" rel="wikipedia">LAMP<&#47;a> Applikationssstack aufsetzen kann. LAMP ist ein Akronym und steht f&uuml;r <a class="zem_slink" title="Linux" href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Linux" rel="wikipedia">Linux<&#47;a>, Apache, MySQL und PHP.</p>
<p>Das folgende Tutorial wurde mit Ubuntu 8.10 durchgef&uuml;hrt. Es wird aber auch mit einer viel &auml;lteren Version funktionieren da sich die grundlegenden Befehle seit Jahren nie ge&auml;ndert haben. Obwohl die Installation relativ simpel ist, sollte dennoch ein Backup angelegt werden. Desweiteren &uuml;bernehme ich auch keine Verantwortung und Support f&uuml;r nicht funktionierende Installationen oder abgeschossene Systeme.</p>
<p>Der Standarduser unter Ubuntu hat schon recht viele Privilegien, f&uuml;r folgende Aktionen werden aber administrative Rechte ben&ouml;tigt. Diese sind nur mit den Rechten eines Superusers m&ouml;glich. Mit Hilfe des sudo-Befehls lassen sich Programme und Befehle mit administrativen Rechten ausf&uuml;hren.</p>
<p>Nachfolgend werden alle ben&ouml;tigten Programme direkt aus der Ubuntu Paketquellen installiert.</p>
<h2><strong>Apache installieren<&#47;strong><&#47;h2><br />
Der Apache Webserver ist in so gut wie jeder Distribution &uuml;ber den Paketmanager verf&uuml;gbar. Unter Ubuntu reichen folgende Befehle um den Apache zu installieren und zu starten.</p>
<pre lang="bash">sudo apt-get install apache2<br />
sudo &#47;etc&#47;init.d&#47;apache2 restart<&#47;pre><br />
Nach abgeschlossener Installation schnell den localhost anpingen oder direkt im Browser aufrufen um zu sehen, ob alles funktioniert. Die Installation ist erfolgreich wenn "It Works!" im Browser erscheint.</p>
<pre lang="bash">#Im Webbrowser folgende URL eingeben<br />
http:&#47;&#47;localhost<&#47;pre><br />
[caption id="" align="alignnone" width="600" caption="It Works!"]<img title="It Works!" src="http:&#47;&#47;nettuts.s3.amazonaws.com&#47;144_WebServer&#47;22.png" alt="It Works!" width="600" height="389" &#47;>[&#47;caption]</p>
<p>Jetzt nur noch schnell die l&auml;stige Fehlermeldung im Terminal entfernen, die jedes mal erscheint, wenn Apache neu gestartet wird.</p>
<pre lang="bash">#im terminal<br />
gksu gedit &#47;etc&#47;apache2&#47;conf.d&#47;fqdn<br />
# diesen text eineben und speichern<br />
ServerName localhost<&#47;pre></p>
<h2><strong>PHP 5 installieren<&#47;strong><&#47;h2><br />
1. Im Terminal folgendes eingeben</p>
<pre lang="bash">sudo apt-get install php5 libapache2-mod-php5<&#47;pre><br />
2. Nachdem die Installation abgeschlossen ist, muss der Apache Webserver neu gestartet werden damit Apache mit PHP 5 l&auml;uft.</p>
<pre lang="bash"># um den apache webserver neu zu starten<br />
sudo &#47;etc&#47;init.d&#47;apache2 restart<&#47;pre><br />
3. So, ich gehe nun davon aus, dass der Apache Webserver problemlos neu gestartet wurde. Nun ist es an der Zeit, zu testen ob PHP 5 &uuml;berhaupt funktioniert.</p>
<pre lang="bash"># in das standard document root wechseln<br />
cd &#47;var&#47;www<br />
# testdatei anlegen<br />
touch index.php<br />
# phpinfo in die datei reinschreiben<br />
echo '<?php phpinfo();' > index.php<&#47;pre><br />
4. Nun noch ein kleiner Check im Browser um zu &uuml;berpr&uuml;fen, dass auch wirklich alles funktioniert hat. Daf&uuml;r einfach folgendes in den Browser eingeben:</p>
<pre lang="bash"># im browser in die adresszeile folgendes eingeben<br />
http:&#47;&#47;localhost&#47;index.php<&#47;pre><br />
5. Es sollten nun bei einer erfolgreichen Konfiguration zahlreiche Informationen zur bestehenden Installation auftauchen.</p>
<h2><strong>MySQL installieren<&#47;strong><&#47;h2><br />
1. Im Terminal folgendes eingeben:</p>
<pre lang="bash">sudo apt-get install mysql-server libapache2-mod-auth-mysql php5-mysql<&#47;pre><br />
2. Am Ende der Installation wird man aufgefordert, ein admin passwort zu setzen. hier kann irgendwas eingegeben werden, man sollte sich aber das Passwort unbedingt merken. Das wars auch schon.</p>
<div class="zemanta-pixie" style="margin-top: 10px; height: 15px;"><a class="zemanta-pixie-a" title="Zemified by Zemanta" href="http:&#47;&#47;reblog.zemanta.com&#47;zemified&#47;04bd4a9e-e65b-40a1-a82f-d3ea643fcca1&#47;"><img class="zemanta-pixie-img" style="float: right;" src="http:&#47;&#47;img.zemanta.com&#47;reblog_e.png?x-id=04bd4a9e-e65b-40a1-a82f-d3ea643fcca1" alt="Reblog this post [with Zemanta]" &#47;><&#47;a><&#47;div></p>
