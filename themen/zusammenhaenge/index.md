Projektzusammenhänge
====================
*[Zur Themenübersicht](../../themen.md)*

Inhalt
======
1. *[Einleitung](#einleitung)*
2. *[Was ist ein Fork?](#was-ist-ein-fork)*
2. *[Untersuchung von Forks](#studie-über-forks)*
3. *[Bekannte Forks](#bekannte-forks)*
4. *[Fazit](#fazit)*

Einleitung
==========
Es liegt in der Natur von Free/Libre Open Source Software (FLOSS) Projekten, dass diese im Zusammenhang stehen zu
anderen FLOSS-Projekten. Diese Zusammenhänge können aus unterschiedlichen Formen bestehen.
Zum einen könnten andere FLOSS-Projekte als Tools in der Entwicklung (zum Beispiel ein Compiler, Paketmanager)
genutzt werden. Auch ist es üblich andere FLOSS-Projekte als Software-Bibliothek ein zu binden und innerhalb des
Projekts auf diese zu zugreifen. Des weiteren kann der Fall auftreten, dass ein anderes FLOSS-Projekt als Inspiration
oder direkter Konkurrent auftritt, der ähnliche Features bietet. Ein besonderes Phänomen in freier Software ist das
Konzept des Forks, auf die in dem folgenden Dokument genauer eingegangen werden soll.


Was ist ein Fork?
=================
Als Fork wird in der freier Software Projekt bezeichnet, welches sich von einem vorher bereits bestehendem Projekt
abgespalten hat und von einer neuen Community betreut wird, die unabhängig vom original Projekt ist.
Der Begriff "Fork" stammt hierbei aus dem POSIX Standard für Betriebssysteme. In diesem ist der Aufruf "fork()"
so definiert, dass der aktuelle Prozess eine Kopie von sich selbst erzeugt worauf hin zwei Kopien dieses Prozesses
existieren, die unabhängig von einander sind. Diese Analogie trifft auch auf Forks in freier Software zu.
Hier existieren nachdem ein fork durchgeführt wurde zwei unabhängige Projekte, die zu einem Zeitpunkt die selbe Code
Basis hatten. Dieses forken ist ein grundlegendes Recht in freier Software. Jedoch soll von diesem Recht nicht ohne
gutem Grund Gebrauch gemacht werden. Es soll eher als ein letzter Ausweg gelten, wenn Konflikte oder
Meinungsverschiedenheiten nicht anders gelöst werden können. Ursprünglich war der Prozess des forken dazu gedacht um
Entwicklern die Möglichkeit zu geben Projekte, die nicht mehr betreut werden weiter zu entwickeln, auch wenn Sie nicht
der Maintainer dieses Projekts sind.


Studie über Forks
================
Im Jahr 2012 wurde das Paper **A Comprehensive Study of Software Forks: Dates, Reasons and Outcomes** von den
Wissenschaftlern **Gregorio Robles** und **Jes´us M. Gonz´alez-Barahona** der King Juan Carlos Universität in Madrid
veröffentlicht. Die Wissenschaftler haben hier Forks näher untersucht und sich dabei auf vier Fragen
konzentriert, die beantwortet werden sollten. Diese Fragen und die Ergebnisse der spanischen Wissenschaftler
werden in den nächsten Abschnitten genauer Erläutert.


Wie viele (relevante) Forks gibt es?
------------------------------------
Zuerst wurde die Frage gestellt, wie viele Forks insgesamt existieren. Dabei war die Hypothese die ursprünglich
aufgestellt wurde, dass Forks selten auftreten. Da Forks in der Open Source Community ein sensibles Thema sind und nur
akzeptiert werden, wenn ein starker Grund für das forken besteht, ist diese Hypothese nachvollziehbar.
Für die Beantwortung dieser Frage haben die Wissenschaftler alle relevanten Forks in der Geschichte freier Software
analysiert. Hierbei wurde relevant auf die Weise definiert, dass ein Fork als relevant gilt, wenn im englischen
Wikipedia ein Eintrag zu diesem Projekt zu finden ist. Dadurch fanden die Wissenschaftler 235 potentielle Forks,
von denen 220 tatsächlich eigenständige Forks sind. Außerdem wird in dem Paper angemerkt, dass Projekte, aus denen
einmal ein Fork entstanden ist dazu tendieren häufiger geforked zu werden. Eine Begründung hierfür sei, dass wenn
bereits einmal der Schritt des forkens gegangen wurde es nicht mehr so starke Begründungen für einen weiteren Fork
bedarf, um akzeptiert zu werden. Des weiteren wird angeführt, dass in allen Bereichen von freier Software Forks
entstehen und diese nicht auf bestimmte Bereiche festgelegt sind.


Entstehen heutzutage häufiger Forks?
------------------------------------
Die zwiete Hypothese, die aufgestellt wurde war, dass heutzutage häufiger Forks entstehen. Eine Begründung hierfür sei
laut den Wissenschaftlern zum einen, dass die absolute Anzahl an FLOSS-Projekten exponentiell gestiegen ist in den
letzten Jahren. Da wäre es nur naheliegend, dass die Anzahl an Forks für diese Projekte ebenfalls ansteigt.
Außerdem werden heutzutage immer mehr FLOSS-Projekte von Firmen betreut, was dazu führen kann, dass die Firma andere
Interessen verfolgt, als die Community des Projekts.

In dem folgenden Diagramm haben die Wissenschaftler dargestellt, wie das Wachstum an Forks seit 1989 bis 2012 verlief.
Dies war der Zeitraum seit dem ersten Fork, aus allen zuvor gefundenen Forks:

<img src="img/oss-forks-per-year.png" />

Aus den Ergebnissen heraus wird deutlich, dass die Anzahl an Forks im laufe der Jahre zwar deutlich gestiegen ist,
jedoch nicht proportional zum Wachstum der Anzahl an FLOSS-Projekten. Stattdessen stieg die Anzahl an Forks eher linear
und nicht exponentiell.


Was sind die Gründe Für Forks?
------------------------------
Eine weitere Frage, die von den Wissenschaftlern beantwortet werden sollte, war nach den Gründen für die Entstehung
von Forks. Hierfür wurden zunächst sechs Kategorien von Gründen definiert, aufgrund dessen ein Projekt geforked werden
kann:
- **Technical:** Diese Kategorie beschreibt den Fall, dass manche Entwickler eine neue Funktionalität in das Projekt
einbauen wollen, jedoch die Verantwortlichen diese Entscheidung nicht unterstützen.
- **More community-driven development:** Hier ist der Grund für eine Abspaltung, dass mehrere Entwickler das Gefühl
haben die Community wird nicht genug einbezogen in die Entwicklung des Projekts. Dies entsteht vor allem bei
FLOSS-Projekten, die von Firmen oder einem einzelnen Maintainer betreut werden.
- **Discontinuation of the original project:** Das ursprüngliche Projekt wird nicht weiter betreut und es entsteht eine
neue Community, die das Projekt weiterführen.
- **Commercial strategy forks:** Ein Fork entsteht auf Grund einer kommerziellen Strategie für das Projekt.
- **Legal issues:** Lizenz Wechsel, Markenrechte oder Änderungen aufgrund von Gesetzen.
- **Differences among developer team:** Die Gruppe von Entwicklern, die das Projekt betreuen sind sich nicht einig über
ein spezielles Thema, welches kein direktes technisches Thema ist.

Nachdem diese Kategorien definiert wurden haben die Wissenschaftler alle Forks, für die Sie einen Grund finden konnten,
jeweils einer Kategorie zugeordnet. Im folgenden sind die Ergebnisse der Analyse in einer Tabelle dargestellt:

<img src="img/oss-forks-reasons.png" />

Es war hierbei möglich bei 9 von 10 Forks den Grund für die Entstehung heraus zu finden. Der häufigste Grund für die
Entstehung eines Forks ist dabei ein technischer Beweggrund. Jedoch sind die Gründe weites gehend über alle
Kategorien verteilt.


Was ist das Resultat von Forks?
-------------------------------
Zuletzt wurde nach den möglichen Resultaten von Forks gefragt. Auch hier wurden mehrere mögliche Resultate definiert
und im Anschluss alle Forks nach diesen Resultaten geprüft, um eine allgemeine Aussage treffen zu können. Die folgenden
Resultate wurden von den Wissenschaftlern definiert:
- Der Fork stirbt.
- Das originale Projekt stirbt.
- Die beiden Projekte werden wieder zusammen geführt.
- Erfolgreiches fortbestehen beider Projekte (Branching).
- Beide Projekte sterben.

Die Hypothese wurde aufgestellt von Wheeler, dass das am häufigsten auftretende Resultat das sterben der Forks ist.
Diese Hypothese wurde bei den Ergebnissen der Analyse wiederlegt. Hier wird klar, dass es annähernd die selbe
Wahrscheinlichkeit ist ob der Fork oder das originale Projekt stirbt. Deutlich wahrscheinlicher war jedoch der Fall,
dass ein erfolgreiches Branching und somit fortbestehen beider FLOSS-Projekte entsteht.

<img src="img/oss-forks-results-pie.png" />

Bekannte Forks
==============
Im folgenden sollen zwei FLOSS-Projekte vorgestellt werden, die Forks sind. Dabei wird beschrieben was die Gründe
für die Entstehung und der Verlauf des Forks beschrieben in Betracht der vorher gewonnenen Ergebnisse.

MariaDB
-------
MariaDB ist ein Relationales Datenbank Managment System (RDBMS) und ist als Fork von dem bekannten Open-Source RDBMS
MySQL entstanden. Die Abspaltung fand 2009 statt aus dem Grund, dass Sun Microsystems von Oracle übernommen wurde.
Durch diese Übernahme war nun auch Oracle verantwortlich für MySQL. Viele Entwickler, unter anderem Michael Widenius,
der Gründer von MySQL, sahen Oracle kritisch im Umgang mit Open-Source Projekten. Deshalb wurde MySQL von Widenius
geforked und MariaDB ist entstanden. MariaDB garantiert dabei eine volle Kompatibilität zu MySQL und implementiert
neue Features von MySQL ebenfalls. Die MariaDB Foundation ist der offizielle Maintainer des MariaDB Projekts.
Wenn wir diesen Fork unter den Kategorien betrachten, die wir zuvor erörtert haben bezüglich dem Resultat von Forks,
fällt MariaDB in die am häufigsten auftretende Kategorie, denn beide Projekte bestehen bis heute und sind viel genutzte
FLOSS-Projekte.

Devuan
------
Devuan ist eine Linux Distribution, die aus einer der bekanntesten Linux Distributionen entstanden ist nämlich Debian.
Der Grund für diesen Fork fällt in die Kategorie "Technical", die zuvor beschrieben wurde. Hierbei war ausschlaggebend,
dass Debian sich dazu entschieden hat, das init-System SysVinit durch das modernere Programm Systemd auszutauschen.
Viele Entwickler haben diese Entscheidung nicht befürwortet. Dies liegt vor allem daran, dass Systemd in der Linux
Community sehr kontrovers ist, weil es mit dem Unix Grundsatz der bricht, dass jedes Programm möglichst simpel sein
soll. Daraus entstand ein Streit unter den Entwicklern, der darin Resultierte, dass 2014 Devuan gegründet wurde
als Fork von Debian mit SysVinit als init-System.

Fazit
=====
Es gibt viele Arten von Zusammenhängen von FLOSS-Projekten. Dabei hebt sich der Fork von den übrigen Arten ab,
denn dadurch wird die Freiheit in diesen Projekte sehr deutlich Characterisiert, weshalb das forken als eines der
grundlegendsten Rechte in freier Software gilt. Das forken von FLOSS-Projekten macht es zum einen möglich für
Entwickler, die ein Projekt weiter führen wollen obwohl dieses von dem ursprünglichen Maintainer nicht mehr
weiter geführt wird. Zum anderen kann die Community ein eigenes Projekt mit der bestehen Code Basis verfolgen,
wenn Sie sich durch eine Firma oder den Maintainer des Ursprungsprojekts nicht unterstützt fühlen.
