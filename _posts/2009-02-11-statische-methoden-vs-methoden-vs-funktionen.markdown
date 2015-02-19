---
layout: post
status: publish
published: true
title: Statische Methoden vs. Methoden vs. Funktionen
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 201
wordpress_url: http://blog.azngeek.de/?p=201
date: !binary |-
  MjAwOS0wMi0xMSAxNTo1Mjo0MCArMDEwMA==
date_gmt: !binary |-
  MjAwOS0wMi0xMSAxMzo1Mjo0MCArMDEwMA==
categories:
- php
- Entwicklung
tags:
- php
- Add new tag
- Programming
- Object-Oriented
comments: []
---
<div class="zemanta-img" style="margin: 1em; display: block;">
<div>
<dl class="wp-caption alignright" style="width: 212px;">
<dt class="wp-caption-dt"><a href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Image:PHP-logo.svg"><img title="PHP" src="http:&#47;&#47;upload.wikimedia.org&#47;wikipedia&#47;en&#47;thumb&#47;2&#47;27&#47;PHP-logo.svg&#47;202px-PHP-logo.svg.png" alt="PHP" width="202" height="107"><&#47;a><&#47;dt>
<dd class="wp-caption-dd zemanta-img-attribution" style="font-size: 0.8em;">Image via <a href="http:&#47;&#47;en.wikipedia.org&#47;wiki&#47;Image:PHP-logo.svg">Wikipedia<&#47;a><&#47;dd> <&#47;dl><&#47;div><br />
<&#47;div><br />
Neulich beim refaktorieren: Ich iteriere ein Array und bei einem bestimmten Index f&uuml;hre ich eine bestimmte Aktion aus. Wie f&uuml;hre ich die Aktion aus, als statische Methode, als Methode nach einer Objektinstanzierung oder als Funktion.Man weiss ja dass Funktionen schneller sind als statische Methoden und diese wiederum schneller als Methoden, doch wie schnell?</p>
<p>Folgendes Skript verdeutlicht die Performanceunterschiede:</p>
<pre line="1" lang="PHP">
  class Test {</p>
<p>	&#47;**<br />
	 * @return The result of 2 + 2 calculation<br />
	 *&#47;</p>
<p>	function testMethod() {<br />
		return 2 + 2;<br />
	}<br />
}</p>
<p>&#47;&#47; A function that returns two plus two<br />
function testFunction() {<br />
	return 2 + 2;<br />
}</p>
<p>&#47;&#47; this will hold the result of callng the method&#47;function<br />
$m = 0;<br />
echo '<br />
<table border="1">
<tbody>
<tr>
<th>Static method<&#47;th></p>
<th>Method with Object creation<&#47;th></p>
<th>Method<&#47;th>
<th>Function<&#47;th></p>
<th>Method vs static bench<&#47;th></p>
<th>Method with Object creation vs static bench<&#47;th></p>
<th>Function vs static bench<&#47;th><br />
      <&#47;tr>';</p>
<p>&#47;&#47; do the test 20 times<br />
for($k = 0; $k < 20; $k ++) {<br />
	echo '<br />
<tr>';<br />
	&#47;&#47; call the method statically<br />
	$start = microtime ();<br />
	for($i = 0; $i < 10000; $i ++) {<br />
		$m = Test::testMethod ();</p>
<p>	}<br />
	$static_time = microtime () - $start;<br />
	echo '
<td>' . $static_time . '<&#47;td>';</p>
<p>	&#47;&#47; call the method "normally"<br />
	$t = new Test ( ); &#47;&#47; create the object outside the loop<br />
	$start = microtime ();</p>
<p>	for($i = 0; $i < 10000; $i ++) {<br />
		$m = $t->testMethod ();<br />
	}</p>
<p>	$method_time = microtime () - $start;</p>
<p>	echo '
<td>' . $method_time . '<&#47;td>';<br />
	&#47;&#47; crete an object inside the loop and call the method<br />
	$start = microtime ();</p>
<p>	for($i = 0; $i < 10000; $i ++) {<br />
		$t2 = new Test ( );<br />
		$m = $t2->testMethod ();<br />
	}</p>
<p>	$mo_time = microtime () - $start;<br />
	echo '
<td>' . $mo_time . '<&#47;td>';<br />
	&#47;&#47; call the function that doeas the same<br />
	$start = microtime ();</p>
<p>	for($i = 0; $i < 10000; $i ++) {<br />
		$m = testFunction ();<br />
	}</p>
<p>	$fn_time = microtime () - $start;<br />
	echo '
<td>' . $fn_time . '<&#47;td>';</p>
<p>	&#47;&#47; ratios<br />
	echo '
<td>' . (($method_time &#47; $static_time) * 100) . '<&#47;td>';<br />
	echo '
<td>' . (($mo_time &#47; $static_time) * 100) . '<&#47;td>';<br />
	echo '
<td>' . (($fn_time &#47; $static_time) * 100) . '<&#47;td>';<br />
	echo '<&#47;tr>';<br />
}<br />
echo '<&#47;tbody><&#47;table>';<br />
<&#47;pre></p>
<p>Und das Resultat:</p>
<pre lang="BASH">Static     Method with  Method                   Method vs      Method with       Function vs<br />
method       Object                 Function     static         Object creation   static<br />
            creation                             bench          vs static bench   bench<br />
------------------------------------------------------------------------------------------------<br />
0.016017    0.016807    0.029788    0.008337    104.932259474   185.977399014     52.05094587<br />
0.01513     0.016974    0.048973    0.014039    112.187706543   323.681427627     92.7891606081<br />
0.025161    0.028501    0.049813    0.013888    113.274512142   197.97702794      55.196534319<br />
0.025065    0.027126    0.050599    0.013764    108.222621185   201.871135049     54.9132256134<br />
0.024057    0.028618    0.050516    -0.991544   118.959138712   209.984619861     -4121.64442782<br />
0.015437    0.01702     0.039125    0.015113    110.254583144   253.449504437     97.9011465958<br />
0.02635     0.032555    0.049082    0.013597    123.548387097   186.269449715     51.6015180266<br />
0.024788    0.027642    0.049174    0.013925    111.51363563    198.378247539     56.1763756656<br />
0.025098    0.027309    0.050644    0.013834    108.80946689    201.785002789     55.1199298749<br />
0.02432     0.028128    0.049716    0.01384     115.657894737   204.424342105     56.9078947368<br />
0.025347    0.028046    0.049223    0.013674    110.648202943   194.19655186      53.9472126879<br />
0.024709    0.026775    0.051406    0.00861     108.361325833   208.045651382     34.8456028168<br />
0.015097    0.017242    0.050361    0.015824    114.208120819   333.582831026     104.815526263<br />
0.027345    0.029153    0.049606    -0.986188   106.611812031   181.407935637     -3606.465533<br />
0.025246    0.027103    0.050693    0.013765    107.355620692   200.796165729     54.5234888695<br />
0.024814    0.02865     0.049334    0.013214    115.459015072   198.815184976     53.2521963408<br />
0.025116    0.028278    0.049423    0.013806    112.589584329   196.778945692     54.9689440994<br />
0.024819    0.027729    0.049891    0.013886    111.72488819    201.019380313     55.949071276<br />
0.025069    0.026437    0.041419    0.008819    105.456938849   165.21999282      35.1789062188<br />
0.015648    0.024254    0.056992    0.014997    154.997443763   364.212678937     95.8397239264<br />
<&#47;pre></p>
<p>Was lernen wir daraus:</p>
<ul>
<li>Eine statische Methode aufzurufen ist doppelt so schnell wie das Instanzieren eines Objektes und dann die Methode aufzurufen.<&#47;li>
<li>Eine statische Methode ist doppelt so schnell als das Instanzieren eines Objektes und dann die Methode aufzurufen nachdme das Objekt bereits existiert.<&#47;li>
<li>Funktionsaufrufe sind doppelt so schnell wie statische Methoden.<&#47;li><br />
<&#47;ul></p>
<div style="margin-top: 10px; height: 15px;" class="zemanta-pixie"><a class="zemanta-pixie-a" href="http:&#47;&#47;reblog.zemanta.com&#47;zemified&#47;e808faca-b426-436d-97e7-5ec846585200&#47;" title="Zemified by Zemanta"><img style="border: medium none ; float: right;" class="zemanta-pixie-img" src="http:&#47;&#47;img.zemanta.com&#47;reblog_e.png?x-id=e808faca-b426-436d-97e7-5ec846585200" alt="Reblog this post [with Zemanta]"><&#47;a><&#47;div></p>
