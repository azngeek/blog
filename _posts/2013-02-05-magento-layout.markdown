---
layout: post
status: publish
published: true
title: Magento Layout
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 541
wordpress_url: http://www.azngeek.de/?p=541
date: !binary |-
  MjAxMy0wMi0wNSAxMTo1ODoxMyArMDEwMA==
date_gmt: !binary |-
  MjAxMy0wMi0wNSAxMDo1ODoxMyArMDEwMA==
categories:
- Allgemein
tags:
- magento
- router
comments: []
---
<p>Wenn ein eigenes Layout verwendet wird folgende Schritte beachten damit die Bl&ouml;cke geladen werden k&ouml;nnen.</p>
<h2>config.xml<&#47;h2><br />
In der config.xml eines Moduls, zum Beispiel <Namespace>&#47;<Model>&#47;etc&#47;config.xml muss folgendes gepr&uuml;ft werden</p>
<ul>
<li>Ist der Name der Route unter frontend&#47;routers eindeutig?<&#47;li>
<li>Gibt es eine Datei, wo die Layout&auml;nderungen gesetzt werden? Zum Beispiel muss sich die Datei don_recipes.xml im Pfad &#47;design&#47;frontend&#47;
<package>&#47;<design>&#47;layout befinden<&#47;li><br />
<&#47;ul></p>
<p>[code lang="xml"]<br />
		<routers><br />
            <recipes> <---- Muss eindeutig sein. Wird nachher in der don_recipes.xml benutzt<br />
                <use>standard<&#47;use><br />
                <args><br />
                    <module>Don_Recipes<&#47;module><br />
                    <frontName>recipes<&#47;frontName><br />
                <&#47;args><br />
            <&#47;recipes><br />
        <&#47;routers><br />
        ------------<br />
		<layout><br />
            <updates><br />
                <Test><br />
                    <file>don_recipes.xml<&#47;file><br />
                <&#47;Test><br />
            <&#47;updates><br />
        <&#47;layout><br />
[&#47;code]</p>
<ul>
<li>Wie ist der Name der Route in der Layout-Datei, in dem Beispiel der don_recipes.xml. Hier gilt: [route]_[index]_[index]<&#47;li><br />
<&#47;ul></p>
<p>[code lang="xml"]<br />
	<layout version="0.1.0"><br />
    <recipes_index_index> <--- [route]_[index]_[index]<br />
        <remove name="left"&#47;><br />
        <remove name="right"&#47;><br />
        <reference name="content"><br />
            <block type="core&#47;template" name="duplicate" template="don&#47;helloworld&#47;index.phtml"&#47;><br />
        <&#47;reference><br />
    <&#47;recipes_index_index><br />
	<&#47;layout><br />
[&#47;code]</p>
