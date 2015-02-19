---
layout: post
status: publish
published: true
title: Fluent Interfaces in PHP
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 28
wordpress_url: http://blog.azngeek.de/?p=28
date: !binary |-
  MjAwOC0wNS0yMCAxNjo1NDowNSArMDIwMA==
date_gmt: !binary |-
  MjAwOC0wNS0yMCAxNDo1NDowNSArMDIwMA==
categories:
- php
tags:
- php
comments:
- id: 1132
  author: Philipp Cordes
  author_email: wipeouter@gmx.de
  author_url: http://www.pcordes.de
  date: !binary |-
    MjAwOS0wMS0yOSAxMzo0Nzo0MiArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMS0yOSAxMTo0Nzo0MiArMDEwMA==
  content: ! "Hallo,\r\n\r\nich habe mich im Zuge meiner Bachelorarbeit sehr intensiv
    mit solchen Fluent Interfaces auseinander gesetzt. In deinem Beitrag verwendest
    du einen eher einfachen Ansatz ein Fluent Interface zu realisieren. Was ist wenn
    du z.B. eine bestimmte Reihenfolge der Methoden erzwingen m&ouml;chtest? In meiner
    Bachelorarbeit habe ich dazu ein Werkzeug erstellt mit dem es nun m&ouml;glich
    ist Diagramme zu erstellen aus denen direkt der n&ouml;tige Programmcode generiert
    werden kann. In den Diagrammen beschreibt man nur noch welche Methode nach welcher
    aufgerufen werden darf. Der Rest wird automatisch generiert. Unter http:&#47;&#47;www.fluent-interfaces.com
    findet man einiges an Material zu meiner L&ouml;sung. Zwar wird zur Zeit nur JAVA
    unterst&uuml;tzt aber eine Portierung f&uuml;r PHP ist durchaus denkbar."
- id: 1133
  author: donbosco
  author_email: donbosco.rulz@gmail.com
  author_url: http://www.azngeek.de
  date: !binary |-
    MjAwOS0wMS0yOSAxNTowOTo1NSArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMS0yOSAxMzowOTo1NSArMDEwMA==
  content: ! "Hallo Philip, \r\n\r\ndanke f&uuml;r deinen Kommentar, du hast mit der
    Aussage nat&uuml;rlich absolut Recht. Es gibt durchaus oft Situationen, in denen
    eine bestimmte Reihenfolge erforderlich ist. So wie ich es gehandhabt habe, ist
    es eher ein simples Method Chaining. Es ist aber auch immer abzuw&auml;gen ob
    das wirklich n&ouml;tig ist. Kann ich zum Beispiel durch meinen Code bereits eine
    richtige Verkettung erzwingen oder muss die implementierte Fluent Interface Klasse
    tats&auml;chlich die Reihenfolge der Verkettung vorgeben. \r\n\r\nMein Beispiel
    oben wird zum Beispiel f&uuml;r REST Interfaces gebraucht. Bei Rest Abfragen spielt
    es nicht eine unbedingt wichtige Roll,e welcher Parameter zuerst kommt. Fluent
    Interfaces wie du sie beschreibst w&uuml;rde ich bei SQL Statements zum Beispiel
    benutzen bzw. tue es dort auch. Hier spielt nat&uuml;rlich die Reihenfolge eine
    wichtige Rolle und ich stimme dir da auch absolut zu. \r\n\r\nBeispielhaft f&uuml;r
    alle Mitleser (Pseudocode)\r\n\r\n$db = new db(); &#47;&#47; datenbankadapter
    erstellen\r\n$query = new Query()->select()->from('tabelle')->params(array('spalte1',
    'spalte2')->where('spalte2' > 2)->limit(5);"
- id: 1134
  author: Philipp Cordes
  author_email: wipeouter@gmx.de
  author_url: http://www.pcordes.de
  date: !binary |-
    MjAwOS0wMS0yOSAxNTo1Njo1MCArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMS0yOSAxMzo1Njo1MCArMDEwMA==
  content: ! "Hallo donbosco,\r\n\r\nda geb ich dir nat&uuml;rlich vollkommen recht.
    Wie bei jedem Pattern muss man immer abw&auml;gen wann es richtig dies einzusetzen.
    \r\n\r\nNur noch eine Anmerkung zum \"einfachen\" Ansatz. Ich habe viele Beispiele
    gesehen in denen die Realisierung des Fluent Interfaces direkt in der Typen vorgenommen
    wird die durch die Verkettung von Methoden ver&auml;ndert werden sollen. Zwar
    mag in diesen Beispielen die Reihenfolge keine Rolle spielen aber es besteht die
    Gefahr, dass wir unsere Entit&auml;ten (z.B. User o.&auml;.), Value Objects etc.
    durch Methoden \"verschmutzen\" die eigentlich garnichts mit diesen zu tun haben.
    Daher bin ich fast immer der Meinung, dass man zumindest das Fluent Interface
    selbst von dem betroffenem Objekt trennen sollte und bei der Schnittstelle nur
    auf bestehende Funktionalit&auml;ten zur&uuml;ckgreifen sollte. \r\n\r\nDas entspricht
    vom Prinzip der Trennung zwischen Services, Entit&auml;ten und Value Objects wie
    man sie aus dem Domain-Driven Design kennt. \r\n\r\nDas soll hier nat&uuml;rlich
    nicht zu einer Regel herhoben werden sondern nur zur Vorsicht mahnen :)"
- id: 1138
  author: donbosco
  author_email: donbosco.rulz@gmail.com
  author_url: http://www.azngeek.de
  date: !binary |-
    MjAwOS0wMi0wMSAwMjo1MjoxMSArMDEwMA==
  date_gmt: !binary |-
    MjAwOS0wMi0wMSAwMDo1MjoxMSArMDEwMA==
  content: ! 'Hallo Phillip,


    danke f&uuml;r deinen ausf&uuml;hrlichen Kommentar. Ich habe die Gelegenheit genutzt,
    mir mehr Gedanken dar&uuml;ber zu machen und den Artikel etwas zu &uuml;berarbeiten.'
---
<p>Seit PHP 5 gibt es die M&ouml;glichkeit ein von einer Methode zur&uuml;ckgegebenes Objekt direkt zu referenzieren. Was das bringt zeig ich in diesem kleinen How To. Ich benutze das ziemlich oft um den Code etwas schlanker zu halten. Zuerst die &uuml;bliche Vorgehensweise. Das folgende Beispiel speichert beliebige Werte in ein eindimensionales Array und mittels der magischen Methode __toString geben wir das Ganze dann aus. Ich habe dieses Beispiel gew&auml;hlt weil ich das tats&auml;chlich in einigen Projekte einsetze und weil es sehr einfach zu verstehen ist. Der Codeschnipsel stammt aus einem Templateparser, der die Aufgabe hat, bestimmte Felder durch bestimmte Werte zu ersetzen. Doch kommen wir einfach gleich mal zum Beispiel.</p>
<pre lang="php" line="1">
class Chain {</p>
<p>privat $_params;</p>
<p>	public function setParam($field, $value)<br />
	{<br />
	$this->_params[$field] = $value;<br />
	}</p>
<p>	public function __toString()<br />
	{<br />
	print_r($this->_params);<br />
	}<br />
}</p>
<p>$chain = new Chain();<br />
$chain->set('field1' , 'value1');<br />
$chain->set('field2', 'value2');<br />
$chain->set('field3', 'value3');<&#47;pre></p>
<p>Was  hier sofort auff&auml;llt, ist dass wir die Methode 'set' immer wieder mit Hilfe des Objekts $chain aufrufen. Das f&uuml;hrt zwangsl&auml;ufig dazu, dass bei mehreren Felder der gleiche Code unn&ouml;tig in die L&auml;nge gezogen wird. Zum Gl&uuml;ck l&auml;sst sich seit PHP5 ein von einer Methode zur&uuml;ckgegebenes Objekt direkt referenzieren. Das Einzige was nun noch ge&auml;ndert werden muss ist der R&uuml;ckgabewert in der Methode 'set'.</p>
<pre lang="php" line="1">
class Chain {</p>
<p>privat $_params;</p>
<p>	public function setParam($field, $value)<br />
	{<br />
		$this->;_params[$field] = $value;<br />
		return $this;<br />
	}</p>
<p>	public function __toString()<br />
	{<br />
		print_r($this->;_params);<br />
	}<br />
}</p>
<p>$chain = new Chain();</p>
<p>$chain->set('feld1', 'wert1')->set('feld2', 'wert2')<&#47;pre><br />
Wie wir nun sehen, hat sich der Code nicht wesentlich ver&auml;ndert, das Skript funktioniert nach wie Vor. Der Unterschied besteht nun darin, dass wir immer ein Objekt direkt referenzieren und damit beliebig viele Methoden nacheinander ausf&uuml;hren k&ouml;nnen. Dies nennt man Fluent Interface.</p>
