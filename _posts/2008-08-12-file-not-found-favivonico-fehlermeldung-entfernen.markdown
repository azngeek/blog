---
layout: post
status: publish
published: true
title: File not found 'favivon.ico' Fehlermeldung entfernen
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: Wenn der Server mal wieder meckert weil das favicon.ico nicht gefunden wurde,
  hilft eventuell folgender Lösungsansatz.
wordpress_id: 47
wordpress_url: http://blog.azngeek.de/?p=47
date: !binary |-
  MjAwOC0wOC0xMiAxMTo1MzoxNyArMDIwMA==
date_gmt: !binary |-
  MjAwOC0wOC0xMiAwOTo1MzoxNyArMDIwMA==
categories:
- Apache
tags:
- apache
- favicon
comments: []
---
<p>Neulich hab ich meine error logs durchsucht und fand interessanterweise hunderte Fehlermeldungen wie diese.</p>
<pre lang="ini">[Tue Aug 12 03:35:08 2008] [error] [client 4.143.177.xxx] File does not exist: &#47;home&#47;domain&#47;favicon.ico<&#47;pre><br />
Super, das sind doch die Fehlermeldungen, auf die man sich immer so richtig freut. Einfach nur mal das Log vollspammen. Nach ein bisschen googlen fand ich folgende L&ouml;sungen.</p>
<p>httpd.conf bzw. die apache2.conf editieren und folgendes hinzuf&uuml;gen</p>
<pre lang="ini">      # Send an 404, if favicon.ico is not available<br />
      Redirect 404 &#47;favicon.ico<br />
      # Don't bother sending the custom error page for favicon.ico</p>
<p>         ErrorDocument 404 "No favicon.ico available"<&#47;pre><br />
oder aber einfach nur ein transparentes favicon herunterladen und in das Wurzelverzeichnis packen.<br />
<a title="favicon.ico" href="http:&#47;&#47;transparentes-favicon.de&#47;favicon.ico">favicon.ico<&#47;a></p>
