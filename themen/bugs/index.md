# Der Umgang mit Bugs
*[Zur Themenübersicht](../../themen.md)*


## **Kurzfassung**
=
In dieser Ausarbeitung wird die Geschichte bzw. die Herkunft von Softwarefehler, häufig auch Bugs (englisch) erläutert. Ebenso soll das Verhältnis zwischen Bugs und deren Organisation/Management innerhalb Free/Libre Open Source Software (FLOSS) übermittelt werden. 
## **Inhaltsverzeichnis**
=
1. [Bugs](#Geschichte)
1.1 [Geschichte](#Geschichte)
1.2 [Definition](#Sefinition)
1.3 [Bugs vs. Features](#Bugs-vs.-features)
2. [Issue-Tracking-System (ITS)](#Issue-tracking-system-(its))
2.1 [Github Issues](#Github-issues)
2.2 [Jira](#Jira)
3. [Security Bugs](#Security-bugs)
4. [Fuzzing](#Fuzzing)
5. [Fazit](#Fazit)
6. [Quellen](#Quellen)
---

**Geschichte** 
Der Begriff "Bug" wurde zum ersten Mal 1946 von Computer-Pionier Grace Hopper verwendet, als sie an den Havard Computern Mark II und Mark III arbeitete. Früher erwiesen sich Computer eher als große Schränke, die aus vielen Schaltern und Relais bestanden. Ein Operator verfolgte einen Fehler im Mark II bis zu einer Motte, die sich in einem Relais verfangen hat. Die Motte wurde entfernt und in das Log-Buch, mit folgender Nachricht versehen: "First actual case of bug being found.", geklebt. Ausgehend vom ersten Bug, werden heutzutage alle Softwarefehler, Bugs genannt. [1]  

**Definition**
Unter einem Software-Bug wird ein unerwünschtes Verhalten bezeichnet, der ein Programm zum Absturz bzw. zu einem invaliden Output führt. Das Problem wird durch unzureichender oder/auch fehlerhafter Logik hervor gerufen. Die Ursache ist häufig menschliches Versagen, die während des Schreibens des Source-Codes oder/auch im Entwicklungsprozess auftritt. [2] Folgen eines Bugs können sehr unterschiedlich sein. Beispiele von Programmfehler innerhalb der FLOSS-Welt werden später behandelt. 

**Bugs vs. Features**
Ein Bug kann als Problem angesehen werden, das Sachen inkludiert, die nicht explizit in den Anforderungen stehen. Im Vergleich dazu ist ein Feature etwas, dass noch nicht angefordert wurde. In vielen Fällen erwartet die Geschäftseinheit, dass etwas gemacht wird, ohne es zu dokumentieren. [4]
Bei der Erkennung sollte es offensichtlich sein, wenn es sich um Bugs handelt, jedoch wird oft gesagt "It's not a bug, it's a feature", da es oft nicht offensichtlich ist. [3]
Ebenso können Bugs im späteren Verlauf auch als Features gesehen werden, wenn zum Beispiel ein Charakter im Computerspiel sich verrückt verhalt und es später zu einem geliebten Feature wird. Andersrum ist das auch möglich, da es verbreitet auftaucht, dass Benutzer unbeliebte Features als Bugs melden. [4] 
Es ist zu sagen das Anforderungen oft nicht ausreichend spezifiziert sind. Code kann nur als "Defekt" gekennzeichnet werden, wenn es sich von den Anforderungen unterscheidet. "Defekte" werden Features genannt, da die Anforderungen oft nie aufgeschrieben wurden. Bugs sollten von der Abweichung von Voraussetzungen abhängen und nicht von subjektiven Vorstellungen. [3]

**Issue-Tracking-System (ITS)**
Es gibt viele Synonyme für Issue-Tracking-System wie z.B. Helpdesk-System, Serviceticket-System, Trouble-Ticket-System, Request-Tracking-System (RTS). [5] Darunter wird Software verstanden, die die Erstellung und Organisation von Cases/Tickets handhabt. Einen ausführlichen Vergleich der Vor- und Nachteile von den Systemen und deren Features wird verzichtet. Dies den Rahmen dieser Ausarbeitung sprengen würde. Stattdessen wird Fokus auf Github Issues gelegt, weil die meisten FLOSS-Projekte dieses ITS nutzen. 

**Github Issues**
Mittels Issues wird die Möglichkeit geschaffen um Überblick über die Aufgaben, Verbesserungen oder Bugs zu behalten. Sie sind sowas wie E-Mails, nur das jeder Zugriff hat und mitdiskutieren kann. Das Spezielle bei diesem ITS ist, dass der Fokus auf die Zusammenarbeit gelegt wurde, durch Referenzierung und Textformatierung. Wenn viele Issues bearbeitet wurden, sind die Filtermöglichkeiten Milestone, Labels und Assignees hilfreich. 
Unter Milestone wird das Erreichen von Etappen besonderer Ziele gekennzeichnet. Labels sind hilfreich um die jeweiligen Issues einzuordnen. Bei Assignees wird jedem Ticket eine Person zugeordnet, die für das jeweilige Issue verantwortlich ist. 
Innerhalb der Kommentarfunktion gibt es eine Funktion @mention, die es dem Benutzer erlaubt, andere Github-Users zu referenzieren. Diese Funktionalität ähnelt dem von Twitter. Durch die @mention-Funktionalität erhält der "ge-@mentionte" Benutzer eine Notification. Die Notifications werden entweder zur jeweiligen E-Mails oder der Weboberfläche von Github geschickt. Notifications werden nicht nur für die @mention Funktion verwendet. Es bietet dem Anwender eine Möglichkeit selbst ausgewählte Issues besser im Auge zu behalten. [7] 

**Jira**
Jira ist ein weiteres ITS, dass einer Webanwendung gleicht. Es wird zur Fehlerverwaltung, Problembehandlung und operativem Projektmanagement, die auch in nicht-technischen Bereichen für das Aufgabenmanagement eingesetzt. Für FLOSS Projekte gibt es eine Open Source Projekt Lizenz, die für FLOSS Projekte frei erworben werden kann. [18]
Entwickelt wurde Jira von der Firma Atlassian [7], die auch Software-Lösungen wie Confluence (kommerzielles Wikipedia)[8] und Bitbucket (kollaborative Versionsverwaltung) [9] entwickelt. Die Funktionsweise von Jira ähnelt der eines Kanban-Boards für agile Softwareentwicklung. Primitive Kanban-Boards haben jeweils eine Spalte "To-Do", "Doing" und "Done". Unterhalb der jeweiligen Spalten werden in der neuen Zeile z.B. Post-Its zu der zugehörigen Spalte der momentanen Bearbeitung geordnet. Die jeweiligen Post-Its beinhalten Informationen zum Bearbeiter, eine Überschrift und eine Beschreibung. 

**Security Bugs**
Ein Security Bug ist ein Fehler, der ausgenutzt wird um unautorisierten Zugang oder Privilegen auf ein Computer System zu erlangen. [10] Diese Bugs führen zu Sicherheitslücken, indem eine oder mehrere der folgenden Faktoren kompromittiert werden: Integrität, Verfügbarkeit und Vertraulichkeit. Integrität beschreibt die Korrektheit von Daten als auch die korrekte Funktionsweise des Systems, Verfügbarkeit beschreibt den Grad des Vorhandenseins des Systems und Vertraulichkeit strebt unautorisierte Informationsgewinnung zu vermeiden. [11] Häufig besitzen Open Source Projekte Dachorganisationen, die das Projekt unterstützen bzw. sogar verwalten. Wird ein Security Bug gefunden, werden diese Bugs häufig der Dachorganisation oder wenn sie eine eigene Website besitzen, dort gemeldet. Je nach Größe des Projekts kann es zu dem dazugehörigen Projekt auch Belohnungen geben, aufgrund des Fundes, der gemeldet wird.
Ein bekanntes Beispiel für ein Security Bug innerhalb von FLOSS ist der sogenannte Heartbleed Bug in OpenSSL. Dabei konnte jeder, Teile des Arbeitsspeichers der Gegenseite auslesen, die nicht selten private Schlüssel, Benutzernamen und/oder Passwörter beinhalteten. Der Kryptologie und Sicherheitsexperte Bruce Schneider beschreibt die Ausmaße des Heartbleed Bugs als: 
"Catastrophic" is the right word. On the scale of 1 to 10, this is an 11. [12]
Gekennzeichnet wurde der Bug mit CVE-2014-0160. Dies ist eine offizielle Referenz, für eine Liste von Einträgen für bekannte Sicherheitsfehler und Sicherheitslücken. [13]

**Fuzzing**
Unter Fuzzing bzw. Fuzz-Testing wird die Methode zum automatisierten Testen von Software verstanden.
Fuzzing wurde an der Universität 1989 zuerst von Barton Miller entwickelt. [14]
Diese Methode prüft Software mit zufälligen Eingaben. Stürzt diese ab, handelt es sich um einen Bug, manchmal auch um eine unentdeckte Sicherheitslücke.
Fuzzing ist einfach durchzuführen. Deshalb bietet es ein gutes Preis-Leistungsverhältnis. Jedoch ist es nicht möglich Programme an einer bestimmten Situation bzw. Anwendungsfall zu testen. 
Google, in Kooperation mit der Core Infrastructure Initiative [16], hat mit ihrem Open Source Fuzzing-Bot, der seit 2016 entwickelt wird, über 9000 Bugs in alltägliche Open Source Projekte gefunden. Davon sind es ungefähr 2000 Security-Bugs. [15] Momentan unterstützt der Fuzzing-Bot nur C und C++ Code und es verspricht Projekten, die sich vom Bot testen lassen, 1000$ für die grundsätzliche Integration und bis zu 20.000$ für eine ideale Integration. Beispielsweise bringt Fuzz-Targets im Upstream-Repository oder eine Code-Coverage von mehr als 80 Prozent jeweils bis zu 5000$. Sie versuchen damit den Zeitaufwand von Entwicklern zu kompensieren, der dabei entsteht. [16]

**Fazit**
Heutzutage gibt es viel Software um den Umgang mit Bugs zu erleichtern. Sowohl in der proprietären als auch in der FLOSS Entwicklung wird viel Wert auf das Management von Bugs/Features durch ITS gelegt. Die Frage nach der richtigen Wahl des Issue-Tracking-System hängt von der Größe des Projekts und von äußerem Einflüsse ab. Wer nach dem großen Geld beim "Bug-Bounty-Hunting" in Open Source Projekten sucht, ist bei proprietäre Software besser aufgehoben. 
Des Weiteren ist Fuzzing eine gute und kostengünstige Möglichkeit Bugs ausfindig zu machen und zu beheben. Deshalb sollten alle in C/C++ geschriebene FLOSS Projekte sich einmal mit dem Fuzzing-Bot beschäftigen und Vor- und Nachteile bewerten. 


**Quellen**
[1]  Etymology (https://en.wikipedia.org/wiki/Software_bug#Etymology)
[2]  Definition - What does  Software Bug  mean? (https://www.techopedia.com/definition/24864/software-bug)
[3] Dalip Mahal, It's Not A Bug, It's...., 04. November 2013, https://dzone.com/articles/its-not-bug-its
[4] John Spacey, Bug vs Feature, 08. November 2017, (https://simplicable.com/new/bug-vs-feature)
[5] Issue-Tracking-System https://de.wikipedia.org/wiki/Issue-Tracking-System
[6] Mastering Issues https://guides.github.com/features/issues/
[7] https://en.wikipedia.org/wiki/Atlassian
[8] https://en.wikipedia.org/wiki/Confluence_(software)
[9] https://en.wikipedia.org/wiki/Bitbucket
[10] https://en.wikipedia.org/wiki/Security_bug
[11] http://www.kryptowissen.de/schutzziele.php
[12] Bruce Schneider, Heartbleed, 09. April 2014,
		https://www.schneier.com/blog/archives/2014/04/heartbleed.html
[13] https://cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0160
[14] https://en.wikipedia.org/wiki/Fuzzing
[15] https://bugs.chromium.org/p/oss-fuzz/issues/list
[16] https://github.com/google/oss-fuzz
[17] Oliver Chang, Abhishek Arya, Kostya Serebryany und Josh Armour, OSS-Fuzz: Five months later, and rewarding projects, 08 .Mai 2017,
		https://security.googleblog.com/2017/05/oss-fuzz-five-months-later-and.html
[18] https://www.atlassian.com/software/views/open-source-license-request
