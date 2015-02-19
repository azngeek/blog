---
layout: post
status: publish
published: true
title: Magento Overwriting Controller
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 601
wordpress_url: http://www.azngeek.de/?p=601
date: !binary |-
  MjAxMy0wNS0wNyAxMDoyMToyNSArMDIwMA==
date_gmt: !binary |-
  MjAxMy0wNS0wNyAwOToyMToyNSArMDIwMA==
categories:
- Allgemein
tags: []
comments: []
---
<div id="container">
<div id="content">
<div id="post-140">
<h2>Autoload and Extended Magento Core Controllers<&#47;h2></p>
<div>
<p>You&rsquo;ll spend a lot of time extending existing classes when you work with Magento to take advantage of the copious built-in functionality. Here is a &lsquo;gotcha&rsquo; when extending controllers:</p>
<p>If you&rsquo;re extending a &lsquo;core&rsquo; factory controller, like so:</p>
<pre lang="PHP">class YourPackage_YourModule_IndexController extends Mage_Adminhtml_Controller_Action<&#47;pre><br />
&hellip;then Adminhtml controller will autoload. However, if you&rsquo;re extending a controller class that is itself extended from a &lsquo;core&rsquo; factory controller, like so:</p>
<pre lang="PHP">class YourPackage_YourModule_IndexController extends Mage_Adminhtml_Report_SalesController<&#47;pre><br />
&hellip;then the SalesController will not autoload. You must include it, like:</p>
<pre lang="PHP">&#47;&#47;refuses to autoload<br />
require_once("Mage&#47;Adminhtml&#47;controllers&#47;Report&#47;SalesController.php");</p>
<p>class YourPackage_YourModule_IndexController extends Mage_Adminhtml_Report_SalesController<&#47;pre><br />
If you&rsquo;re having trouble getting access to the controller class that you&rsquo;ve extended, this may be the problem.</p>
<p>&nbsp;</p>
<p>http:&#47;&#47;stackoverflow.com&#47;questions&#47;7491150&#47;why-doesnt-magento-autoload-parent-class</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<div>
<p>The Magento autoloader is a simple "replace underscores with slashes" algorithm. Because Zend Framework names its controllers differently, and because Magento uses parts of Zend and is inspired by Zend in others, it's controllers are named with Zend conventions and placed in a <code>controllers<&#47;code> folder, meaning the standard auto load routine won't work.</p>
<p>It ends up controller classes are automatically included during Magento's <a href="http:&#47;&#47;alanstorm.com&#47;category&#47;magento#dispatch">routing process<&#47;a> but NOT by the PHP auto loader. Instead, there's custom PHP code to handle this.</p>
<p>So, during routing, because you've told Magento to use your controllers instead of Magento's controller for a particular request, it's the only controller that gets included.</p>
<p>Best guess is the request for controller overrides caught the original developers off guard, and while they've been happy to jury rig a solution with routing, it hasn't been a priority to refactor the controller autoload code.</p>
<p><&#47;div><br />
<&#47;div><br />
<&#47;div><br />
<&#47;div><br />
<&#47;div></p>
