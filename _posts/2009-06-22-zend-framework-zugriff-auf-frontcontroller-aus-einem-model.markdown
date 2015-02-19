---
layout: post
status: publish
published: true
title: ! 'Zend Framework: Zugriff auf FrontController aus einem Model'
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 221
wordpress_url: http://www.azngeek.de/allgemein/zend-framework-zugriff-auf-frontcontroller-aus-einem-model/
date: !binary |-
  MjAwOS0wNi0yMiAxNToyMzoxMSArMDIwMA==
date_gmt: !binary |-
  MjAwOS0wNi0yMiAxMzoyMzoxMSArMDIwMA==
categories:
- Allgemein
tags: []
comments: []
---
<p>$this->_frontController = Zend_Controller_Front::getInstance();</p>
<p>Da der FrontController das Singleton implementiert, ist der Zugriff auf den FrontController innerhalb eines Models ein Kinderspiel. Es muss dementsprechend nur die bereits vorhandene Instanz geholt werden und schon stehen der gesamter FrontController im Model zur Verf&uuml;gung.</p>
