---
layout: post
status: publish
published: true
title: Wissenschaftliches Arbeiten mit der FOM-Vorlage auf dem Mac
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: ! "<h1>Latex auf dem Mac zu installieren ist nicht so schwer<&#47;h1>\r\nLatex
  auf dem Mac zu installieren ist nicht so schwer.\r\n<h2>Download<&#47;h2>\r\nZuerst
  auf die Seite <a href=\"http:&#47;&#47;www.tug.org&#47;mactex&#47;2011&#47;\">MacTex<&#47;a>
  navigieren und dann die aktuelle Distribution herunterladen. Normalerweise tr&auml;gt
  sie die Bezeichnung <em>MacTex.mpkg.zip<&#47;em>. Der Download ist ziemlich gro&szlig;
  und betr&auml;gt circa 1.8GB (Stand 30. July 2011). Jetzt kannst du die Zeit nutzen
  und zum Beispiel dir folgendes Buch anschauen: <a href=\"http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3826658922&#47;ref=as_li_qf_sp_asin_tl?ie=UTF8&amp;tag=azngeek-21&amp;linkCode=as2&amp;camp=1638&amp;creative=6742&amp;creativeASIN=3826658922\">Latex
  Handbuch<&#47;a><img style=\"border: none !important; margin: 0px !important;\"
  src=\"http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&amp;l=as2&amp;o=3&amp;a=3826658922\"
  alt=\"\" width=\"1\" height=\"1\" border=\"0\" &#47;>.\r\n\r\n"
wordpress_id: 405
wordpress_url: http://azngeek.de/?p=5
date: !binary |-
  MjAxMS0xMi0xMCAxMzozNDozMCArMDEwMA==
date_gmt: !binary |-
  MjAxMS0xMi0xMCAxMzozNDozMCArMDEwMA==
categories:
- Allgemein
tags: []
comments:
- id: 1858
  author: Bachelor Thesis auf dem Mac schreiben | bartkowiak punkt de
  author_email: ''
  author_url: http://www.bartkowiak.de/archives/1062
  date: !binary |-
    MjAxMi0xMi0yNiAxMzo1NzoxOCArMDEwMA==
  date_gmt: !binary |-
    MjAxMi0xMi0yNiAxMjo1NzoxOCArMDEwMA==
  content: ! '[...] Gl&uuml;ck hat sich schon jemand die M&uuml;he gemacht und im
    letzten Jahr aufgeschrieben, wie man das alles installiert und konfiguriert bekommt.
    Wenn das immer noch Fragezeichen hinterl&auml;sst, ich kenne da einen Professor
    an der FOM, [...]'
---
<h1>Latex auf dem Mac zu installieren ist nicht so schwer<&#47;h1><br />
Latex auf dem Mac zu installieren ist nicht so schwer.</p>
<h2>Download<&#47;h2><br />
Zuerst auf die Seite <a href="http:&#47;&#47;www.tug.org&#47;mactex&#47;2011&#47;">MacTex<&#47;a> navigieren und dann die aktuelle Distribution herunterladen. Normalerweise tr&auml;gt sie die Bezeichnung <em>MacTex.mpkg.zip<&#47;em>. Der Download ist ziemlich gro&szlig; und betr&auml;gt circa 1.8GB (Stand 30. July 2011). Jetzt kannst du die Zeit nutzen und zum Beispiel dir folgendes Buch anschauen: <a href="http:&#47;&#47;www.amazon.de&#47;gp&#47;product&#47;3826658922&#47;ref=as_li_qf_sp_asin_tl?ie=UTF8&amp;tag=azngeek-21&amp;linkCode=as2&amp;camp=1638&amp;creative=6742&amp;creativeASIN=3826658922">Latex Handbuch<&#47;a><img style="border: none !important; margin: 0px !important;" src="http:&#47;&#47;www.assoc-amazon.de&#47;e&#47;ir?t=azngeek-21&amp;l=as2&amp;o=3&amp;a=3826658922" alt="" width="1" height="1" border="0" &#47;>.</p>
<p><a id="more"></a><a id="more-405"></a></p>
<h2>Installation<&#47;h2><br />
Das MacText-Paket muss nach der Installation einfach nur entpackt werden. Die Installation dauert ein paar Minuten. <img src="http:&#47;&#47;img.skitch.com&#47;20111210-tqsjskab7wenw7r3te4r2uic9a.jpg" alt="http:&#47;&#47;img.skitch.com&#47;20111210-tqsjskab7wenw7r3te4r2uic9a.jpg" &#47;></p>
<p><img src="https:&#47;&#47;img.skitch.com&#47;20111210-rrwwdc3rtps45qajit7awcfy85.jpg" alt="https:&#47;&#47;img.skitch.com&#47;20111210-rrwwdc3rtps45qajit7awcfy85.jpg" &#47;></p>
<h2>Fom-Paket<&#47;h2><br />
Das entsprechende FOM-Latex-Paket kann unter folgender URL runtergealden werden: . Wichtig f&uuml;r den Download ist die gesamte <a href="http:&#47;&#47;www.plexdata.de&#47;fomsdt&#47;download&#47;fomsdt_v01.08.zip">Datei<&#47;a>.</p>
<p>Das beigef&uuml;gte PDF enth&auml;lt zwar eine ausf&uuml;hrliche Dokumentation f&uuml;r die Installation unter Linux und Windows Plattformen, Unix, insbesondere aber die Eigenheiten von MAC-OS bzw. MacTex werden nicht ber&uuml;cksichtigt. Als Erstes ist der Latex-Pfad unter MAC-Os zu identifizieren. Es gibt &uuml;brigens keine Variable $TEXROOT, zumindest wird sie nicht per Default gesetzt. Braucht man aber auch nicht. Das Standardverzeichnis ist bei TexMac immer &#47;usr&#47;local&#47;texlive. Jedes Extra-Paket wird unter &#47;usr&#47;local&#47;texlive&#47;texmf-local installiert.</p>
<p>[bash]<br />
&#47;usr&#47;local&#47;texlive&#47;texmf-local<br />
[&#47;bash]</p>
<h3>Pfade erstellen<&#47;h3><br />
Die Pfade m&uuml;ssen erst mal erstellt werden. Zu beachten ist dass sich MacTex unter root einrichtet. Also hier jeweils mit sudo arbeiten.</p>
<p>[bash]<br />
cd &#47;usr&#47;local&#47;texlive&#47;texmf-local<br />
sudo mkdir tex&#47;latex&#47;fomsdt<br />
sudo mkdir -p makeindex&#47;fomsdt<br />
[&#47;bash]</p>
<h3>Kopieren und entpacken<&#47;h3><br />
Nachdem zuvor die Zielverzeichnisse, wie in Abschnitt 3.1 be- schrieben, erstellt wurden, werden die zum Paket geh&ouml;ren- den Dateien fomsdt.ins und fomsdt.dtx von ihrer Quelle, beispielsweise das Verzeichnis, in welchem die Dateien nach ihrem Download gespeichert wurden, in das Verzeichnis &#47;usr&#47;local&#47;texlive&#47;tex&#47;latex&#47;fomsdt kopiert.</p>
<p>[bash]<br />
# ins download-verzeichnis wechseln<br />
sudo cp fomsdt.dtx fomsdt.ins &#47;usr&#47;local&#47;texlive&#47;texmf-local&#47;tex&#47;latex&#47;fomsdt&#47;<br />
[&#47;bash]</p>
<p>Jetzt wird im Verzeichnis &#47;usr&#47;local&#47;texlive&#47;texmf-local&#47;tex&#47;latex&#47;fomsdt eine Shell beziehungsweise Konsole ge&ouml;ffnet und darin der Befehl zum Entpacken des Pakets wie folgt eingegeben und ausge- f&uuml;hrt:</p>
<p>[bash]<br />
#sudo pdflatex fomsdt.ins<br />
[&#47;bash]</p>
<p>Jetzt nur noch die Datei fomidx.ist verschieben</p>
<p>[bash]<br />
sudo mv fomidx.ist &#47;usr&#47;local&#47;texlive&#47;texmf-local&#47;makeindex&#47;fomsdt&#47;<br />
[&#47;bash]</p>
<h3>Aktualisierung der Umgebungen<&#47;h3><br />
[bash]$ sudo texhash[&#47;bash]</p>
<h2>Fom-Update Pakete zur Einhaltung der Richtlinien<&#47;h2></p>
