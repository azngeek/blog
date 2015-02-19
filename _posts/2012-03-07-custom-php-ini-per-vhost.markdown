---
layout: post
status: publish
published: true
title: Custom php.ini per VHost
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 533
wordpress_url: http://www.azngeek.de/?p=533
date: !binary |-
  MjAxMi0wMy0wNyAxMTo1NDo0NSArMDEwMA==
date_gmt: !binary |-
  MjAxMi0wMy0wNyAxMDo1NDo0NSArMDEwMA==
categories:
- php
- Apache
- quickwin
tags: []
comments: []
---
<h1>How to create a custom php.ini per vhost<&#47;h1></p>
<p>[code]<br />
<VirtualHost www.yourdomain.de:80></p>
<p>PHPINIDir &#47;your&#47;phpini&#47;directory</p>
<p><&#47;VirtualHost><br />
[&#47;code]</p>
