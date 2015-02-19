---
layout: post
status: publish
published: true
title: PhpStorm 3.0 - Increase Memory Heap Size
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
excerpt: Testest
wordpress_id: 478
wordpress_url: http://www.azngeek.de/?p=78
date: !binary |-
  MjAxMi0wMS0wNCAxMDo0NjowNiArMDEwMA==
date_gmt: !binary |-
  MjAxMi0wMS0wNCAxMDo0NjowNiArMDEwMA==
categories:
- Allgemein
tags: []
comments: []
---
<p>PhpStorm braucht eine ganze Menge Speicher. Unter MacOS kann beim Indexieren gro&szlig;e Projekte schon mal der Speicher knapp werden. Einfach im Ordner Programme den Paketinhalt von PhpStorm anzeigen lassen,</p>
<p>unter Contents navigieren und die Info.plst &ouml;ffnen.</p>
<p>Folgenden Eintrag &auml;ndern und freuen:</p>
<p>-Xms128m -Xmx1400m -XX:MaxPermSize=350m -XX:ReservedCodeCacheSize=64m -XX:+UseCompressedOops</p>
