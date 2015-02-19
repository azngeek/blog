---
layout: post
status: publish
published: true
title: Magento Layout Handles
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 585
wordpress_url: http://www.azngeek.de/?p=585
date: !binary |-
  MjAxMy0wMi0wOCAxMjoyNjo1NCArMDEwMA==
date_gmt: !binary |-
  MjAxMy0wMi0wOCAxMToyNjo1NCArMDEwMA==
categories:
- Allgemein
tags:
- magento
- Layout Handles
comments: []
---
<p>Interessant,</p>
<p>in meiner Recherche bin ich auf folgendes gesto&szlig;en. In Magento k&ouml;nnen Layout-Handles in den Layout-Konfigurationsdateien gesetzt werden, um &Auml;nderungen an der Struktur und Inhalt einer Seite durchzuf&uuml;hren.</p>
<h2>Beispiel<&#47;h2><br />
Das sind alle m&ouml;glichen Layout-Handles</p>
<p>[code lang="php"]</p>
<p>class Mage_Widget_Model_Widget_Instance extends Mage_Core_Model_Abstract<br />
...<br />
    const DEFAULT_LAYOUT_HANDLE            = 'default';<br />
    const PRODUCT_LAYOUT_HANDLE            = 'catalog_product_view';<br />
    const SINGLE_PRODUCT_LAYOUT_HANLDE     = 'PRODUCT_{{ID}}';<br />
    const PRODUCT_TYPE_LAYOUT_HANDLE       = 'PRODUCT_TYPE_{{TYPE}}';<br />
    const ANCHOR_CATEGORY_LAYOUT_HANDLE    = 'catalog_category_layered';<br />
    const NOTANCHOR_CATEGORY_LAYOUT_HANDLE = 'catalog_category_default';<br />
    const SINGLE_CATEGORY_LAYOUT_HANDLE    = 'CATEGORY_{{ID}}';<br />
...<br />
[&#47;code]</p>
<h2>Anwendung<&#47;h2></p>
<p>[code lang="xml"]<br />
   <catalog_category_default> <--- In dem Fall wird das Handle NOTANCHOR_CATEGORY_LAYOUT_HANDLE ausgef&uuml;hrt<br />
        <!-- Anwenden der &Auml;nderungen in --><br />
        <!-- dem Layoutupdate-Handle <move_sidebar_cart> --><br />
        <update handle="move_sidebar_cart"&#47;><br />
    <&#47;catalog_category_default><br />
[&#47;code]</p>
