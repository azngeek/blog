---
layout: post
status: publish
published: true
title: XAMPP Ordner werden nicht angezeigt
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: ! 'Bei einer neuen XAMPP Installation kommt es oft vor, dass einige Ordner
  nicht im Browser angezeigt werden. Das hat einfach damit zu tun, dass das mod_rewrite
  module nicht aktiviert ist. '
wordpress_id: 41
wordpress_url: http://blog.azngeek.de/?p=41
date: !binary |-
  MjAwOC0wNy0yNCAxMzo1NjoyMSArMDIwMA==
date_gmt: !binary |-
  MjAwOC0wNy0yNCAxMTo1NjoyMSArMDIwMA==
categories:
- Apache
tags:
- php
- apache
- xampp
comments: []
---
<p>Dieses Problem tritt immer auf, wenn man XAMPP von apachefriends.org installiert, sich seine Projekte anschauen m&ouml;chte und feststellt, dass s&auml;mtliche ORdner, die eine .htaccess enthalten, nicht angezeigt werden. Die L&ouml;sung ist ziemlich simpel, das mod_rewrite Modul ist einfach nicht aktiviert, dadurch werden die Ordner alle nicht angezeigt.</p>
<p>Einfach nur in der httpd.conf den Eintrag mod_rewrite suchen und das auskommentierte entfernen. Ziemlich easy, passiert mir auch alle paar Monate mal, nur wissen sollte man es.</p>
<pre lang="ini">httpd.conf</p>
<p>#LoadModule rewrite_module modules&#47;mod_rewrite.so &#47;&#47; auskommentieren</p>
<p>LoadModule rewrite_module modules&#47;mod_rewrite.so   &#47;&#47; so ist es richtig<&#47;pre><br />
Ein kurzer Blick in die phpinfo() h&auml;tte auch das Ergebnis gebracht, aber eventuell hilft das ja irgend jemanden mal.</p>
<pre lang="php">info.php</p>
<p>phpinfo();<&#47;pre></p>
