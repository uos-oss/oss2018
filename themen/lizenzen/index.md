# Ein Überblick über FLOSS-Lizenzen

*[Zur Themenübersicht](../../themen.md)*

## Gliederung

* [Vorwort](#vorwort)
* [Definition Lizenz](#def-lizenz)
* [Open Source](#open-source)
	* [Definition der OSI](#osi-Definition)
	* [Definition von Richard M. Stallman und die FSF](#richard-m.-s-tallman-und-fsf)
	* [Häufige Beschreibungen im Bereich Open Source](#abgrenzung)
* [FLOSS Lizenztypen](#lizenztypen)
	* [Permissive](#permissive)
	* [Copyleft](#copyleft)
	* [Glossar zu Lizenzen](#begriffe)
* [Lizenzbeispiele](#beispiele)
	* [WTFPL](#wtfpl)
	* [MIT](#mit)
	* [Apache 2.0](#apache-2.0)
	* [GNU GPLv3](#gnu-gplv3)
* [choosealicence.com](#choosealicence)
* [Kompatibilität von Lizenzen](#kompatibilitaet)
* [SPDX zur Kenntlichmachung von Lizenzen](#vorstellung-von-spdx)

<a name="#vorwort"/>

## Vortwort

Diese Ausarbeitung, wie auch die zu diesem Thema gehaltene Präsentation, erheben keinen Anspruch auf Vollständigkeit und Richtigkeit der dargestellten Themenaspekte. Es wird außerdem jegliche Haftung für lizenztechnisches Fehlverhalten ausgeschlossen. Der Ersteller dieses Dokumentes ist kein Anwalt mit lizenztechnischer Expertise, sondern ein Studenten des Bachelorstudiengangs Informatik der Universität Osnabrück.

Des Weiteren werden wichtige Begriffe größtenteils in Englisch gehalten, da es sich im Bereich Open Source um eine international agierende Gemeinschaft handelt. Beschreibungen der verwendeten Begriffe werden vorwiegend auf Deutsch gegeben.

Außerdem handelt es sich hierbei um eine Grobszusammenfassung der Thematik. Sinn ist es nicht Expertenwissen zu vermitteln, sondern einen groben Überblick über die Thematik der Lizenzen für Quellcode im Open-Source-Bereich zu geben.

Viel Spaß beim Lesen, Lernen und Durchklicken.

<a name="def-lizenz"/>

## Definition Lizenz

Aufgrund der häufigen Verwendung des Begriffs "Lizenz" bereits zu Beginn der Ausarbeitung wird zunächst eine definiton von Lizenzen vorgestellt ohne näher auf die in diesem Zusammenhang häufig verwendeten Begrifflichkeiten einzugehen. Dies dient der Verständlichkeit der im folgenden vorgestellten Definitionen von Open Soure und den daraus resultierenden Lizenzen.

[Definition(DE)](https://wirtschaftslexikon.gabler.de/definition/lizenz-38383): die vom Inhaber eines gewerblichen Schutzrechts oder urheberrechtlichen Verwertungsrechts einem Dritten eingeräumte Befugnis, die dem Rechtsinhaber zustehenden Verwertungsrechte auszuüben (Nutzungsrecht).

Unformal ausgedrückt handelt es sich bei einer Lizenz also um eine schriftlich festgehaltene Erklärung, in welcher beschrieben wird, wie der Umgang mit dem erstellten Sourcecode geregelt ist. In Deutschland hat automatisch der Ersteller des Sourcecodes einen Copyright-Anspruch und muss die Erlaubnis zur freien Benutzung, Änderung und Weiterverbreitung Anderer erst explizit gewähren. Dadurch sind die rechtlichen Konsequenzen der Benutzung eindeutig festgelegt. Diese Erlaubnis stellt eine Lizenz dar. Lizenzen reichen in ihrer Beschreibung von sehr simplen Formulierungen, bestehend aus wenigen Bedingungen, bis hin zu komplexen Rechtstexten. Näheres in [Abschnitt](#beispiele).

In dieser Ausarbeitung werden lediglich FLOSS-Lizenzen (Free/Libre Open Source Software Lizenzen) behandelt. Was genau FLOSS bedeutet wird im folgenden Abschnitt erläutert.

<a name="open-source"/>

## Open Source

Was genau Open Source Software Entwicklung bedeutet, ist noch immer eine ab und an debattierte Fragestellung. Dennoch haben sich heutzutage einige wenige international etablierte Organisationen herauskirstallisiert, welche ihre jeweilige Definiton von Open Source verbreiten und schützen.

FLOSS (Free/Libre Open Source Software) bezeichnet hierbei zur Vereinfachung im Folgenden immer den Zusammenschluss aller anerkannter Open Source Bewegungen.

<a name="osi-Definition"/>

### Definition der OSI

Die durch die [Open Source Initiative (OSI)](https://opensource.org/) formulierte Definition ist neben der von Richard Stallman verfassten Definition eine der am weltweit Anerkanntesten und gliedert sich in insgesamt 10 [Regeln](https://opensource.org/docs/osd), welche Software erfüllen muss, um als Open Source gelten zu dürfen.

#### Die 10 Regeln

1. **Free Redistribution**: Die Lizenz darf niemanden darin hindern, die Software zu verkaufen oder sie mit anderer Software zusammen in einer Software-Distribution weiterzugeben. Die Lizenz darf keine Lizenzgebühr verlangen.
2. **Source Code**: Die Software muss im Quellcode für alle Nutzer verfügbar sein.
3. **Derived Works**: Die Lizenz muss von der Basissoftware abgeleitete Arbeiten und deren Distribution unter derselben Lizenz wie die Basissoftware erlauben.
4. **Integrity of The Author’s Source Code**: Die Lizenz muss explizit das Verteilen von Software erlauben, die auf einer modifizierten Version des Originalquellcodes beruhen. Die Lizenz kann verlangen, dass solche Änderungen zu einem neuen Namen oder einer neuen Versionsnummer der Software führen und dokumentiert werden. Die Lizenz darf verlangen, dass nur Patches zum Originalcode verteilt werden dürfen, wenn diese mit dem Quellcode verteilt werden dürfen.
5. **No Discrimination Against Persons or Groups**: Die Lizenz darf nicht einzelnen Personen oder Gruppen die Nutzung der Software verweigern, z. B. den Bürgern eines bestimmten Staates.
6. **No Discrimination Against Fields of Endeavor**: Die Lizenz darf den Verwendungszweck der Software nicht einschränken, z. B. kein Ausschluss militärischer oder kommerzieller Nutzung o. Ä.
7. **Distribution of License**: Die Lizenz muss für alle verfügbar sein, welche die Software erhalten, ohne z. B. eine Registrierung oder eine andere Lizenz erwerben zu müssen.
8. **License Must Not Be Specific to a Product**: Die Lizenz muss produktneutral gestaltet sein und darf sich z. B. nicht auf eine bestimmte Distribution beziehen.
9. **License Must Not Restrict Other Software**: Sie darf zum Beispiel nicht verlangen, dass sie nur mit Open Source Software verbreitet werden darf.
10. **License Must Be Technology-Neutral**: Sie darf z. B. nicht verlangen, dass die Distribution nur via Web/CD/DVD verteilt werden darf oder nur auf Intel-Plattformen laufen soll.

<a name="richard-m.-s-tallman-und-fsf"/>

### Definition von Richard M. Stallman und die FSF

Richard M. Stallman gründete am 4. Oktober 1985 die [Free Software Foundation](https://www.fsf.org/), um sein Bild freier Software zu verbreiten. Konkret konzipierte er dazu die erste Version einer der bekanntesten Open Source Lizenzen, die [GNU GPLv1](https://www.gnu.org/licenses/old-licenses/gpl-1.0), deren Eigenschaten in späterem Kapitel genauer betrachtet und beurteilt werden. Diese Lizenz garantiert die von Stallman verfassten vier Freiheiten.

[Die 4 Freiheiten](https://www.gnu.org/philosophy/free-sw), welche Software einhalten muss um laut FSF als frei bezeichnet werden zu dürfen:

#### Freedom 0

*Die Freiheit, das Programm auszuführen wie man möchte, für jeden Zweck.*

"Die Freiheit, das Programm auszuführen" bedeutet für jegliche Person oder Organisation die Freiheit zu haben, es auf jedem beliebigen Rechner für jede Art von Aufgabe und Zweck nutzen zu dürfen, ohne darüber mit dem Entwickler oder irgendeinem Unternehmen kommunizieren zu müssen. In dieser Freiheit ist der Nutzer das Ziel, nicht der Entwickler! Dem Nutzer steht es frei das Programm für eigene Zwecke auszuführen, und wenn man es an jemand anderen weitergibt, steht es dieser Person dann frei es für eigene Zwecke auszuführen, aber man ist nicht berechtigt, ihr eigene Absichten aufzuerlegen.

"Die Freiheit, das Programm auszuführen wie man möchte" bedeutet, dass einem nicht untersagt oder davon abgehalten wird, es auszuführen. Dies hat nichts mit der Funktionalität des Programm zu tun, ob es technisch dazu in der Lage ist in einer bestimmten Umgebung zu funktionieren oder ob es für einen bestimmten Bereich der Datenverarbeitung sinnvoll ist.

#### Freedom 1

*Die Freiheit, die Funktionsweise des Programms zu untersuchen und eigenen Datenverarbeitungbedürfnissen anzupassen.*

Freiheit 1 umfasst die Freiheit, die eigene geänderte Version anstelle des Originals zu verwenden. Kommt das Programm in einem Produkt zum Einsatz, in dem die modifizierte Version eines Dritten, nicht jedoch die eigene ‑ eine als Tivoisierung bzw. Abriegelung (engl. ‚Lockdown‘) oder (in seiner praktizierenden perversen Terminologie) als „Secure Boot“ bekannte Praxis ‑  ausgeführt wird, wird Freiheit 1 eher zu einem fadenscheinigen Vorwand anstatt einer praktischen Realität. Diese Binärdateien sind nicht freie Software, selbst wenn der Quellcode, von dem sie kompiliert werden, frei ist.
Die Zusammenführung der verfügbaren freien Unterroutinen und -modulen ist eine wichtige Möglichkeit ein Programm zu modifizieren. Wenn die Programmlizenz eines entsprechend lizenzierten vorhandenen Moduls die Zusammenführung untersagt ‑ beispielsweise wenn man nicht der Copyrightinhaber des hinzuzufügenden Quellcodes ist ‑ dann ist die Lizenz zu restriktiv, um sich als frei zu qualifizieren.
Ob eine Änderung eine Verbesserung darstellt, ist eine subjektive Angelegenheit. Wenn das Recht ein Programm zu modifizieren im Wesentlichen auf Änderungen beschränkt wird, die jemand anderes als Verbesserung betrachtet, ist das Programm unfrei.

#### Freedom 2

*Die Freiheit, das Programm zu redistribuieren und damit Mitmenschen zu helfen.*

"Die Freiheit, das Programm zu redistribuieren und […] der Öffentlichkeit freizugeben" (Freiheit 2 und 3) bedeutet, dass man die Freiheit hat Kopien an jedermann überall weiterzugeben (entweder mit oder ohne Modifikationen, gratis oder gegen Gebühr für den Vertrieb). Frei sein bedeutet, diese Dinge (unter anderem) vornehmen zu können, ohne fragen oder für die Berechtigung zahlen zu müssen.

Außerdem sollte man auch die Freiheit haben Modifikationen vorzunehmen und privat im eigenen Werk oder Spiel zu nutzen, ohne auch nur deren Existenz zu erwähnen. Veröffentlicht man die Änderungen, sollte es nicht erforderlich sein, irgendjemand im Besonderen oder auf irgendeine bestimmte Weise zu benachrichtigen.

"Die Freiheit, Programmkopien aufs neue zu distribuieren" muss binäre oder ausführbare Formen des Programms als auch den Quellcode für modifizierte und unmodifizierte Versionen beinhalten (die Distribution von Programmen in ausführbarer Form ist für bequem installierbare freie Betriebssysteme notwendig). Es ist in Ordnung, wenn es für bestimmte Anwendungen keine Möglichkeit gibt eine Binärdatei oder ausführbare Form zu erstellen (da einige Programmiersprachen diese Funktion nicht unterstützen), aber man muss die Freiheit haben solche Formen an Dritte weiterzugeben, sollte man eine Möglichkeit finden oder entwickeln, sie zu erstellen.

#### Freedom 3

*Die Freiheit, das Programm zu verbessern und diese Verbesserungen der Öffentlichkeit freizugeben, damit die gesamte Gesellschaft davon profitiert.*

Freiheit 3 umfasst die Freiheit, eigene modifizierte Versionen als Freie Software freizugeben. Eine freie Lizenz kann auch andere Möglichkeiten der Freigabe zulassen. Mit anderen Worten muss es sich nicht um eine Lizenz mit [Copyleft](#copyleft) handeln. Allerdings qualifiziert sich eine Lizenz, die von modifizierten Versionen verlangt unfrei zu sein, nicht als freie Lizenz.

#### Abgrenzung der Free Software Bewegung zur Open Source Bewegung

Die FSF grenzt ihre Definition [wie folgt](https://www.gnu.org/philosophy/free-software-for-freedom.de.html) ab:

> Eine andere Gruppierung verwendet den Begriff „Open Source“ um etwas ähnliches (aber nicht identisches) wie Freie Software zu meinen.
> Die FSF bevorzugt den Begriff Freie Software, denn, sobald man gehört hat, dass sich dieser auf Freiheit statt auf den Preis bezieht, ruft es Freiheit in Erinnerung.
> Das Wort offen bezieht sich niemals auf Freiheit. "

Somit geht es bei dieser Definition verstärkt um die Philosophie der Free-Software-Bewegung und den damit einhergehenden Pflichten der Entwickler.

<a name="abgrenzung"/>

### Häufige Beschreibungen im Bereich Open Source

![](img/grobe_abgrenzung.png?raw=true)

Wie auf dem Bild zu erkennen, bedeutet Open Source nicht immer dasselbe. "Open Source" allgemein kann ebenfalls Software enthalten, welche nicht FLOSS ist aber deren Source Code dennoch offen einsehbar ist. Open-Source-Lizenzen nach OSI können in einigen Fällen nicht von der FSF als solche anerkannt sein und umgekehrt. Der Begriff der Freeware wurde aufgrund der Namensgebung und der Verwechslungsgefahr mit eingefügt. Bei Freeware handelt es sich lediglich um kostenlose Software. Diese Grafik ist als eine vereinfachte Darstellung zu betrachten.

<a name="lizenztypen"/>

## FLOSS Lizenztypen

FlOSS-Lizenzen lassen sich generell auf einem Spektrum von sehr Permissive (dt. Freizügig) bis Copy-Left anordnen. Es folgen genauere Erläuterungen hierzu, sowie ein kurzes Glossar oft in Lizenzen vorkommender Begriffe.

<a name="permissive"/>

### Permissive

Permissive Lizenzen beinhalten kaum oder keine Restriktionen für den Lizenznehmer, also denjenigen, welcher die von jemand anderem geschriebene, frei zugängliche Software, benutzen, modifizieren oder neu verbreiten möchte. Meist ist unter Permissive Lizenzen sogar die Benutzung innerhalb propriätärer Software möglich.

#### Sonderfall Public Domain

Public Domain oder auch gemeinfrei ist ein komplexes rechtliches Konzept, welches oft in verschiedenen Ländern verschieden interpretiert wird und somit generell umgangen werden sollte. Die Nichtexistenz einer Lizenz für ein Softwareprojekt bedeutet in Deutschland nicht, dass damit automatisch alle anderen Benutzer die selben Rechte wie der Ersteller des Codes genießen. In Deutschland hat der Ersteller des Sourcecode automatisch das Copyright für seine Kreation. Um rechtliche Probleme zu vermeiden, sollte der Ersteller explizit mithilfe einer Lizenz klarstellen, was erlaubt und was nicht erlaubt ist.

Weitere Probleme können mit Public Domain auftreten.

* Kein Patentschutz
* Kein Trademarkschutz
* Die Inkludierung von Public Domain Software in eigenem Projekt kann rechtlich heikel sein
* Ob eine Software Public Domain ist, ist nicht immer ersichtlich
* Ob die Four Freedoms gewährleistet sind, ist nicht ersichtlich
* Public Domain ist keine *OSI-approved copyright license*

<a name="copyleft"/>

### Copyleft

Copyleft als Gegenstück zum Copyright verpflichtet dazu, jegliche Änderungen des Originalcodes wieder unter der ursprünglichen Lizenz zu Lizensieren. Die Lizenz wird also vererbt. Dies hat gewisse Vor- und Nachteile. Zum einen wird somit verhindert, dass sich unter anderem Firmen freier Software bereichern, diese für ihre Zwecke nutzen und verändern, aber niemals positiv zum Ursprungsprojekt beitragen. Es ist also keine Ausbeutung des Originalgerstellers möglich. Zum anderen wird ggf. der Nutzungsbereich derer Entwickler eingeschränkt, die die Software innerhalb von propriätärer Software benutzen und verbreiten möchten.

<a name="begriffe"/>

### Glossar zu Lizenzen

<div>
<table>
<tr>
    <td> <b> Commercial use</b> </td>
    <td>Software kann in kommerziellem Umfeld benutzt werden. Das muss nicht automatisch bedeuten, dass sie in proprietärer Software benutzt werden darf. Dies wird über das Vorhanden- oder Nichtvorhandensein von Copyleft-Bedingungen geregelt.</td>
<tr>
<tr>
	<td> <b> Distribution</b></td>
	<td>Software kann von Anderen wiederverbreitet werden.</td>
</tr>
<tr>
	<td> <b> Modification</b> </td>
	<td>Software kann verändert und für den eigenen Nutzen angepasst werden.</td>
</tr>
<tr>
	<td> <b> Patent use</b> </td>
	<td>Die Software kann ohne rechtliche Konsequenzen genutzt werden, selbst wenn sie Patente des Erstellers enthält. </td>
</tr>
<tr>
	<td> <b> Private use</b> </td>
	<td>Software kann für Privatzwecke benutzt und verändert werden.</td>
</tr>
<tr>
	<td> <b> Disclose source</b> </td>
	<td>Bei Veröffentlichung der Software muss der Sourcecode mitveröffentlicht werden.</td>
</tr>
<tr>
	<td> <b> License and copyright notice</b> </td>
	<td>Der Software liegt die Lizenz sowie eine Copyright Notice bei.</td>
</tr>
<tr>
	<td> <b> Network use is distribution</b> </td>
	<td>Selbst wenn Benutzer der Software diese nur über ein Netzwerk nutzt (z.B. über das Internet), gilt dies als Verbreitung. Dies kann dazu führen, dass selbst Nutzern, welche nur so die Software benutzen, der Sourcecode mit Lizenz und Copyright Notice zusteht.</td>
</tr>
<tr>
	<td> <b> Same license</b> </td>
	<td>Abgeleitete Software muss mit derselben oder ggf. einer ähnlichen Lizenz wie das Original versehen werden.</td>
</tr>
<tr>
	<td> <b> State changes</b> </td>
	<td>Veränderungen am Sourcecode müssen dokumentiert werden.</td>
</tr>
<tr>
	<td> <b>Liability</b> </td>
	<td>Die lizenz enthält eine Erklärung zur limitierten Haftung.</td>
</tr>
<tr>
	<td> <b> Warrenty</b> </td>
	<td>Die Lizenz beschreibt eindeutig, dass für die Software keine Garantie und keine Gewähr geleistet wird.</td>
</tr>
<tr>
	<td> <b> Trademark use</b> </td>
	<td>Die Lizenz beschreibt eindeutig, dass keine Trademarkrechte der Software oder des entwickelnden Unternehmens übergeben werden.</td>
</tr>
</table>
</div>

<a name="beispiele"/>

## Lizenzbeispiele

Im Folgenden werden einige Lizenzen vorgestellt. Die getroffene Auswahl soll beginnend von sehr simplen und Permissive Lizenzen bis hin zu komplexeren Lizenzen mit Copy-Left, ein Generelles und konkretes Bild darüber geben, welche Lizenzen in der echten Welt Anwendung finden.

Einen Überblick über alle gängigen Lizenzen ist auf der [webseite](https://spdx.org/licenses/) des SPDX-Projektes zu finden.

<a name="wtfpl"/>

### WTFPL

Die ursprünglich von Banlu Kemiyatorn und in zweiter Version von [Sam Hocevar](https://en.wikipedia.org/wiki/Sam_Hocevar) erstellte ["Do What The Fuck You Want Public Licence" (WTFPL)](https://spdx.org/licenses/WTFPL.html) stellt wohl die freizügiste Lizenz, die man konstruieren kann, dar. Sie umfasst lediglich eine einzige Bedingung in welcher beschrieben steht, dass man tun kann "was zur Hölle man möchte" (What the Fuck You Want). Es handelt sich hierbei zwar um eine spassige Herangeghensweise an das Konzept einer freizügigen Lizenz, dennoch ist diese wohl in den meisten Teilen der Welt rechtlich anerkannt. Durch sie wird der Code ohne jegliche Restriktionen der Öffentlichkeit ausgestellt und hat somit den Character einer Public-Domain-ähnlichen Lizenz. WTFPL wird momentan für etwa [790.000 Dateien](https://github.com/search?utf8=%E2%9C%93&q=%22WTFPL%22&type=Code&ref=searchresults) und Projekte auf Github benutzt und findet überwiegend in Kleinst- oder Klein-projekten Gebrauch. Wenn Software mit professionellem Anspruch entwickelt wird, sollte allerdings auf eine rechtlich erpropte und internationalisierte Lizenz zurückgegriffen werden. Ein Beispiel dafür ist die MIT-Lizenz welche in folgendem Abschnitt vorgestellt wird.

Die OSI erkennt die WTFPL [nicht an](https://opensource.org/minutes20090304). Das FSF hingegen stuft sie als eine Freie Lizenz ein.

#### Der vollständige Lizenztext der WTFPL

	DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
	        Version 2, December 2004

	Copyright (C) 2004 Sam Hocevar
	14 rue de Plaisance, 75014 Paris, France
	Everyone is permitted to copy and distribute verbatim or modified
	copies of this license document, and changing it is allowed as long
	as the name is changed.

	DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
	TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

	0. You just DO WHAT THE FUCK YOU WANT TO.

#### Eigenschaften

<table>
 <tr>
  <th>Erlaubt</th>
  <th>Bedingungen</th>
  <th>Begrenzung</th>
 </tr>
 <tr>
  <td>
  	<ul>
  		<li>Commercial use</li>
  		<li>Distribution</li>
  		<li>Modification</li>
  		<li>Private use</li>
  		<li>Patent use</li>
  	</ul>
  </td>
  <td>
  	<ul>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>Liability</li>
  		<li>Warranty</li>
  		<li>Trademark use</li>
  	</ul>
  </td>
 </tr>
</table>


<a name="mit"/>

### MIT

Die vom [MIT](http://web.mit.edu/) entwickelte [MIT-Lizenz](https://spdx.org/licenses/MIT.html#licenseText) stellt eine Permissive Lizenz dar und ist die auf GitHub meistverwendete Lizenz. Sie ist einfach gehalten und somit leicht verständlich.

Die MIT-Lizenz wird unter anderem von folgenden Projekten benutzt.

* Rust (Doppellizenz)
* Node.js
* Ruby on Rails
* GitLab
* PuTTY

#### Eigenschaften

<table>
 <tr>
  <th>Erlaubt</th>
  <th>Bedingungen</th>
  <th>Begrenzung</th>
 </tr>
 <tr>
  <td>
  	<ul>
  		<li>Commercial use</li>
  		<li>Distribution</li>
  		<li>Modification</li>
  		<li>Private use</li>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>License und Copyright notice muss Software beigefügt werden</li>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>Liability</li>
  		<li>Warranty</li>
  	</ul>
  </td>
 </tr>
</table>


<a name="apache-2.0"/>

### Apache 2.0

Die von der [Apache Software Foundation (ASF)](https://www.apache.org/) verfassten [Apache Licence](https://spdx.org/licenses/Apache-2.0.html) stellt eine weiter Permissive Lizenz da. Im Gegensatz zur MIT-Lizenz müssen bei Verwendung der Apache-Lizenz Änderungen als solche erkenntlich gemacht werden. Ausserdem wird in ihr zusätzlich das Nutzen von Patenten geregelt und ein expliziter Ausschluss der Übertragung und Verwendung von Markenzeichen formuliert.

Die Apache-2.0-Lizenz wird unter anderem von folgenden Projekten benutzt.

* Rust (Doppellizenz)
* Swift
* Android
* Apache HTTP Server
* Docker

#### Eigenschaften

<table>
 <tr>
  <th>Erlaubt</th>
  <th>Bedingungen</th>
  <th>Begrenzung</th>
 </tr>
 <tr>
  <td>
  	<ul>
  		<li>Commercial use</li>
  		<li>Distribution</li>
  		<li>Modification</li>
  		<li>Private use</li>
  		<li>Patent use</li>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>License und Copyright notice muss Software beigefügt werden</li>
  		<li>Änderungen am Code müssen dokumentiert sein</li>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>Liability</li>
  		<li>Warranty</li>
  		<li>Trademark use</li>
  	</ul>
  </td>
 </tr>
</table>

<a name="gnu-gplv3"/>

### GPLv3

Die [General Public Licence (GPL)](https://spdx.org/licenses/GPL-3.0-only.html) wurde in ihrer ersten Version 1998 von [Richard Matthew Stallman](https://en.wikipedia.org/wiki/Richard_Stallman) veröffentlicht und befindet sich momentan in ihrer dritten Version. Sie wurde zum Schutz der [4 Freiheiten](https://www.gnu.org/philosophy/free-sw) konzipiert und stellt eine Copy-Left-Lizenz da. Abgeleitete Software darf also nur unter derselben oder einer ebenbürtigen Lizenz weiterverbreitet werden. Sie ist der Standard, wenn es darum geht zu garantieren, dass die 4 Freiheiten eingehalten werden, da die Benutzung im Gegensatz zu den bisher vorgestellten Lizenzen dazu zwingt, "seinem Mitmenschen zu helfen" und sich nicht nur an der bereitgestellten Software zu bereichern.

Die GPL wird unter anderem von folgenden Projekten benutzt.

* uBlock Origin
* bash
* Signal
* Linux (GPLv2)

#### Eigenschaften

<table>
 <tr>
  <th>Erlaubt</th>
  <th>Bedingungen</th>
  <th>Begrenzung</th>
 </tr>
 <tr>
  <td>
  	<ul>
  		<li>Commercial use</li>
  		<li>Distribution</li>
  		<li>Modification</li>
  		<li>Private use</li>
  		<li>Patent use</li>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>Source Code</li>
  		<li>Vererbung der Lizenz</li>
  		<li>License und Copyright notice muss Software beigefügt werden</li>
  		<li>Änderungen am Code müssen dokumentiert sein</li>
  	</ul>
  </td>
  <td>
  	<ul>
  		<li>Liability</li>
  		<li>Warranty</li>
  	</ul>
  </td>
 </tr>
</table>

<a name="choosealicence"/>

### choosealicence.com

Das für die vorgestellten Lizenzen verwendete Vergleichsschema richtet sich stark nach dem des von [choosealicense.com](https://choosealicense.com/) verwendeten Charakterisierungsverfahren. Diese Website ist ein Projekt GitHubs und stellt die wichtigsten Lizenzen anhand einer anschaulichen Zusammenfassung vor und erleichtert somit die Wahl einer zu den eigenen Ansprüchen passsenden Lizenz. Dies geschieht anhand des Stellens einiger Fragen bezüglich der individuellen Bedürfnisse im Bezug auf die zu lizenzierende Software.

<a name="kompatibilitaet"/>

### Kompatibilität

Lizenzen können zu anderen kompatibel sein, es kann also Software der einen Lizenz auch mit einer anderen neu lizensiert werden. Eine Änderung der Lizenz kann allerdings auch negative Folgen nach sich ziehen, wenn der ursprüngliche Code bereits von anderen Akteuren gebraucht wird. Deshalb ist es wichtig, sich bereits zu Beginn Gedanken über die Wahl einer passenden Lizenz zu machen. Welche Lizenzen miteinander kompatibel sind ist beispielhaft auf folgender Grafik zu sehen. Die Lizenz mit abgehendem Pfeil ist zu der Lizenz kompatibel zu der dieser Pfeil führt. Die Pfeilrichtung ist dabei zu beachten, d.h. wenn Lizenz A zu Lizenz B kompatibel ist bedeutet dies nicht, dass auch Lizenz B zu A kompatibel ist. (Quelle: [Grafik](https://dwheeler.com/essays/floss-license-slide.html) von David A. Wheeler)

<a href="https://dwheeler.com/essays/floss-license-slide-image.png"><img src="https://dwheeler.com/essays/floss-license-slide-image.png" alt="Grafik zur Kompatibilität von Lizenzen" /></a>

<a name="vorstellung-von-spdx"/>

### SPDX zur Kenntlichmachung von Lizenzen

[Software Package Data Exchange (SPDX)](https://spdx.org/) ist ein Dateiformat, anhand dessen eindeutig erkennbar sein soll, insbesondere auch für Maschinen, welche Lizenz der Sourcecode innehat. SPDX wird von der SPDX Working Group entwickelt, welche wiederum unter der Schirmherrschaft der Linux Foundation steht.

Jede Lizenz bekommt einen vollen Namen sowie ein eindeutiges Kürzel zugewiesen. Dieser Name wird zu Beginn der Lizenzerklärung eingefügt, und kann dann maschinell von anderen Programmen ausgewertet werden. Als Beispiel kann hier GitHub aufgeführt werden. Wenn der SPDX-Identifier bei einer Lizensierung genutzt wird, so erscheint die Lizenz automatisch in der Kurzbeschreibung des Projektes. Ausserdem wird ggf. eine Liste der Eigenschaften, wie sie auf der Webseite [choosealicence.com](https://choosealicense.com/) zu finden ist, angezeigt.
