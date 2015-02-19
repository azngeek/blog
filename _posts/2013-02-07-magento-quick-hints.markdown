---
layout: post
status: publish
published: true
title: Magento Quick Hints
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 579
wordpress_url: http://www.azngeek.de/?p=579
date: !binary |-
  MjAxMy0wMi0wNyAxNTo0NzoyMCArMDEwMA==
date_gmt: !binary |-
  MjAxMy0wMi0wNyAxNDo0NzoyMCArMDEwMA==
categories:
- Allgemein
tags: []
comments: []
---
<p>Layouts:</p>
<p>Jedes Modul sollte seine eigene Layout-Datei haben. Sonst k&ouml;nne es passieren, dass ein Layout pro Modul geladen wird. </p>
<p>Beispiel:</p>
<p>Modul 1 greift auf Layout A zu -> schlecht<br />
Modul 2 greift auf Layout B zu -> schlecht</p>
