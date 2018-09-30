---


---

<h1 id="der-umgang-mit-bugs">Der Umgang mit Bugs</h1>
<p><em><a href="../../themen.md">Zur Themenübersicht</a></em></p>
<h2 id="kurzfassung"><strong>Kurzfassung</strong></h2>
<p>In dieser Ausarbeitung wird die Geschichte bzw. die Herkunft von Softwarefehler, häufig auch Bugs (englisch) erläutert. Ebenso soll das Verhältnis zwischen Bugs und deren Organisation/Management innerhalb Free/Libre Open Source Software (FLOSS) übermittelt werden.</p>
<h2 id="inhaltsverzeichnis"><strong>Inhaltsverzeichnis</strong></h2>
<ol>
<li><a href="#geschichte">Bugs</a><br>
1.1 <a href="#geschichte">Geschichte</a><br>
1.2 <a href="#definition">Definition</a><br>
1.3 <a href="#bugs-vs.-features">Bugs vs. Features</a></li>
<li><a href="#issue-tracking-system">Issue-Tracking-System</a><br>
2.1 <a href="#github-issues">Github Issues</a><br>
2.2 <a href="#jira">Jira</a></li>
<li><a href="#security-bugs">Security Bugs</a></li>
<li><a href="#fuzzing">Fuzzing</a></li>
<li><a href="#fazit">Fazit</a></li>
<li><a href="#quellen">Quellen</a></li>
</ol>
<h2 id="geschichte"><strong>Geschichte</strong></h2>
<p>Der Begriff “Bug” wurde zum ersten Mal 1946 von Computer-Pionier Grace Hopper verwendet, als sie an den Havard Computern Mark II und Mark III arbeitete. Früher erwiesen sich Computer eher als große Schränke, die aus vielen Schaltern und Relais bestanden. Ein Operator verfolgte einen Fehler im Mark II bis zu einer Motte, die sich in einem Relais verfangen hat. Die Motte wurde entfernt und in das Log-Buch, mit folgender Nachricht versehen: “First actual case of bug being found.”, geklebt. Ausgehend vom ersten Bug, werden heutzutage alle Softwarefehler, Bugs genannt. [1]</p>
<h2 id="definition"><strong>Definition</strong></h2>
<p>Unter einem Software-Bug wird ein unerwünschtes Verhalten bezeichnet, der ein Programm zum Absturz bzw. zu einem invaliden Output führt. Das Problem wird durch unzureichender oder/auch fehlerhafter Logik hervor gerufen. Die Ursache ist häufig menschliches Versagen, die während des Schreibens des Source-Codes oder/auch im Entwicklungsprozess auftritt. [2] Folgen eines Bugs können sehr unterschiedlich sein. Beispiele von Programmfehler innerhalb der FLOSS-Welt werden später behandelt.</p>
<h2 id="bugs-vs.-features"><strong>Bugs vs. Features</strong></h2>
<p>Ein Bug kann als Problem angesehen werden, das Sachen inkludiert, die nicht explizit in den Anforderungen stehen. Im Vergleich dazu ist ein Feature etwas, dass noch nicht angefordert wurde. In vielen Fällen erwartet die Geschäftseinheit, dass etwas gemacht wird, ohne es zu dokumentieren. [4]<br>
Bei der Erkennung sollte es offensichtlich sein, wenn es sich um Bugs handelt, jedoch wird oft gesagt “It’s not a bug, it’s a feature”, da es oft nicht offensichtlich ist. [3]<br>
Ebenso können Bugs im späteren Verlauf auch als Features gesehen werden, wenn zum Beispiel ein Charakter im Computerspiel sich verrückt verhalt und es später zu einem geliebten Feature wird. Andersrum ist das auch möglich, da es verbreitet auftaucht, dass Benutzer unbeliebte Features als Bugs melden. [4]<br>
Es ist zu sagen das Anforderungen oft nicht ausreichend spezifiziert sind. Code kann nur als “Defekt” gekennzeichnet werden, wenn es sich von den Anforderungen unterscheidet. “Defekte” werden Features genannt, da die Anforderungen oft nie aufgeschrieben wurden. Bugs sollten von der Abweichung von Voraussetzungen abhängen und nicht von subjektiven Vorstellungen. [3]</p>
<h2 id="issue-tracking-system"><strong>Issue-Tracking-System</strong></h2>
<p>Es gibt viele Synonyme für Issue-Tracking-System (kurz: ITS) wie z.B. Helpdesk-System, Serviceticket-System, Trouble-Ticket-System, Request-Tracking-System (RTS). [5] Darunter wird Software verstanden, die die Erstellung und Organisation von Cases/Tickets handhabt. Einen ausführlichen Vergleich der Vor- und Nachteile von den Systemen und deren Features wird verzichtet. Dies den Rahmen dieser Ausarbeitung sprengen würde. Stattdessen wird Fokus auf Github Issues gelegt, weil die meisten FLOSS-Projekte dieses ITS nutzen.</p>
<h2 id="github-issues"><strong>Github Issues</strong></h2>
<p>Mittels Issues wird die Möglichkeit geschaffen um Überblick über die Aufgaben, Verbesserungen oder Bugs zu behalten. Sie sind sowas wie E-Mails, nur das jeder Zugriff hat und mitdiskutieren kann. Das Spezielle bei diesem ITS ist, dass der Fokus auf die Zusammenarbeit gelegt wurde, durch Referenzierung und Textformatierung. Wenn viele Issues bearbeitet wurden, sind die Filtermöglichkeiten Milestone, Labels und Assignees hilfreich.<br>
Unter Milestone wird das Erreichen von Etappen besonderer Ziele gekennzeichnet. Labels sind hilfreich um die jeweiligen Issues einzuordnen. Bei Assignees wird jedem Ticket eine Person zugeordnet, die für das jeweilige Issue verantwortlich ist.<br>
Innerhalb der Kommentarfunktion gibt es eine Funktion @mention, die es dem Benutzer erlaubt, andere Github-Users zu referenzieren. Diese Funktionalität ähnelt dem von Twitter. Durch die @mention-Funktionalität erhält der “ge-@mentionte” Benutzer eine Notification. Die Notifications werden entweder zur jeweiligen E-Mails oder der Weboberfläche von Github geschickt. Notifications werden nicht nur für die @mention Funktion verwendet. Es bietet dem Anwender eine Möglichkeit selbst ausgewählte Issues besser im Auge zu behalten. [6]</p>
<h2 id="jira"><strong>Jira</strong></h2>
<p>Jira ist ein weiteres ITS, dass einer Webanwendung gleicht. Es wird zur Fehlerverwaltung, Problembehandlung und operativem Projektmanagement, die auch in nicht-technischen Bereichen für das Aufgabenmanagement eingesetzt. Für FLOSS Projekte gibt es eine Open Source Projekt Lizenz, die für FLOSS Projekte frei erworben werden kann. [18]<br>
Entwickelt wurde Jira von der Firma Atlassian [7], die auch Software-Lösungen wie Confluence (kommerzielles Wikipedia)[8] und Bitbucket (kollaborative Versionsverwaltung) [9] entwickelt. Die Funktionsweise von Jira ähnelt der eines Kanban-Boards für agile Softwareentwicklung. Primitive Kanban-Boards haben jeweils eine Spalte “To-Do”, “Doing” und “Done”. Unterhalb der jeweiligen Spalten werden in der neuen Zeile z.B. Post-Its zu der zugehörigen Spalte der momentanen Bearbeitung geordnet. Die jeweiligen Post-Its beinhalten Informationen zum Bearbeiter, eine Überschrift und eine Beschreibung.</p>
<h2 id="security-bugs"><strong>Security Bugs</strong></h2>
<p>Ein Security Bug ist ein Fehler, der ausgenutzt wird um unautorisierten Zugang oder Privilegen auf ein Computer System zu erlangen. [10] Diese Bugs führen zu Sicherheitslücken, indem eine oder mehrere der folgenden Faktoren kompromittiert werden: Integrität, Verfügbarkeit und Vertraulichkeit. Integrität beschreibt die Korrektheit von Daten als auch die korrekte Funktionsweise des Systems, Verfügbarkeit beschreibt den Grad des Vorhandenseins des Systems und Vertraulichkeit strebt unautorisierte Informationsgewinnung zu vermeiden. [11] Häufig besitzen Open Source Projekte Dachorganisationen, die das Projekt unterstützen bzw. sogar verwalten. Wird ein Security Bug gefunden, werden diese Bugs häufig der Dachorganisation oder wenn sie eine eigene Website besitzen, dort gemeldet. Je nach Größe des Projekts kann es zu dem dazugehörigen Projekt auch Belohnungen geben, aufgrund des Fundes, der gemeldet wird.<br>
Ein bekanntes Beispiel für ein Security Bug innerhalb von FLOSS ist der sogenannte Heartbleed Bug in OpenSSL. Dabei konnte jeder, Teile des Arbeitsspeichers der Gegenseite auslesen, die nicht selten private Schlüssel, Benutzernamen und/oder Passwörter beinhalteten. Der Kryptologie und Sicherheitsexperte Bruce Schneider beschreibt die Ausmaße des Heartbleed Bugs als:<br>
“Catastrophic” is the right word. On the scale of 1 to 10, this is an 11. [12]<br>
Gekennzeichnet wurde der Bug mit CVE-2014-0160. Dies ist eine offizielle Referenz, für eine Liste von Einträgen für bekannte Sicherheitsfehler und Sicherheitslücken. [13]</p>
<h2 id="fuzzing"><strong>Fuzzing</strong></h2>
<p>Unter Fuzzing bzw. Fuzz-Testing wird die Methode zum automatisierten Testen von Software verstanden.<br>
Fuzzing wurde an der Universität 1989 zuerst von Barton Miller entwickelt. [14]<br>
Diese Methode prüft Software mit zufälligen Eingaben. Stürzt diese ab, handelt es sich um einen Bug, manchmal auch um eine unentdeckte Sicherheitslücke.<br>
Fuzzing ist einfach durchzuführen. Deshalb bietet es ein gutes Preis-Leistungsverhältnis. Jedoch ist es nicht möglich Programme an einer bestimmten Situation bzw. Anwendungsfall zu testen.<br>
Google, in Kooperation mit der Core Infrastructure Initiative [16], hat mit ihrem Open Source Fuzzing-Bot, der seit 2016 entwickelt wird, über 9000 Bugs in alltägliche Open Source Projekte gefunden. Davon sind es ungefähr 2000 Security-Bugs. [15] Momentan unterstützt der Fuzzing-Bot nur C und C++ Code und es verspricht Projekten, die sich vom Bot testen lassen, 1000$ für die grundsätzliche Integration und bis zu 20.000$ für eine ideale Integration. Beispielsweise bringt Fuzz-Targets im Upstream-Repository oder eine Code-Coverage von mehr als 80 Prozent jeweils bis zu 5000$. Sie versuchen damit den Zeitaufwand von Entwicklern zu kompensieren, der dabei entsteht. [16]</p>
<h2 id="fazit"><strong>Fazit</strong></h2>
<p>Heutzutage gibt es viel Software um den Umgang mit Bugs zu erleichtern. Sowohl in der proprietären als auch in der FLOSS Entwicklung wird viel Wert auf das Management von Bugs/Features durch ITS gelegt. Die Frage nach der richtigen Wahl des Issue-Tracking-System hängt von der Größe des Projekts und von äußerem Einflüsse ab. Wer nach dem großen Geld beim “Bug-Bounty-Hunting” in Open Source Projekten sucht, ist bei proprietäre Software besser aufgehoben.<br>
Des Weiteren ist Fuzzing eine gute und kostengünstige Möglichkeit Bugs ausfindig zu machen und zu beheben. Deshalb sollten alle in C/C++ geschriebene FLOSS Projekte sich einmal mit dem Fuzzing-Bot beschäftigen und Vor- und Nachteile bewerten.</p>
<h2 id="quellen"><strong>Quellen</strong></h2>
<p>[1]  Etymology (<a href="https://en.wikipedia.org/wiki/Software_bug#Etymology">https://en.wikipedia.org/wiki/Software_bug#Etymology</a>)<br>
[2]  Definition - What does  Software Bug  mean? (<a href="https://www.techopedia.com/definition/24864/software-bug">https://www.techopedia.com/definition/24864/software-bug</a>)<br>
[3] Dalip Mahal, It’s Not A Bug, It’s…, 04. November 2013, <a href="https://dzone.com/articles/its-not-bug-its">https://dzone.com/articles/its-not-bug-its</a><br>
[4] John Spacey, Bug vs Feature, 08. November 2017, (<a href="https://simplicable.com/new/bug-vs-feature">https://simplicable.com/new/bug-vs-feature</a>)<br>
[5] Issue-Tracking-System <a href="https://de.wikipedia.org/wiki/Issue-Tracking-System">https://de.wikipedia.org/wiki/Issue-Tracking-System</a><br>
[6] Mastering Issues <a href="https://guides.github.com/features/issues/">https://guides.github.com/features/issues/</a><br>
[7] <a href="https://en.wikipedia.org/wiki/Atlassian">https://en.wikipedia.org/wiki/Atlassian</a><br>
[8] <a href="https://en.wikipedia.org/wiki/Confluence_(software)">https://en.wikipedia.org/wiki/Confluence_(software)</a><br>
[9] <a href="https://en.wikipedia.org/wiki/Bitbucket">https://en.wikipedia.org/wiki/Bitbucket</a><br>
[10] <a href="https://en.wikipedia.org/wiki/Security_bug">https://en.wikipedia.org/wiki/Security_bug</a><br>
[11] <a href="http://www.kryptowissen.de/schutzziele.php">http://www.kryptowissen.de/schutzziele.php</a><br>
[12] Bruce Schneider, Heartbleed, 09. April 2014,<br>
<a href="https://www.schneier.com/blog/archives/2014/04/heartbleed.html">https://www.schneier.com/blog/archives/2014/04/heartbleed.html</a><br>
[13] <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0160">https://cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0160</a><br>
[14] <a href="https://en.wikipedia.org/wiki/Fuzzing">https://en.wikipedia.org/wiki/Fuzzing</a><br>
[15] <a href="https://bugs.chromium.org/p/oss-fuzz/issues/list">https://bugs.chromium.org/p/oss-fuzz/issues/list</a><br>
[16] <a href="https://github.com/google/oss-fuzz">https://github.com/google/oss-fuzz</a><br>
[17] Oliver Chang, Abhishek Arya, Kostya Serebryany und Josh Armour, OSS-Fuzz: Five months later, and rewarding projects, 08 .Mai 2017,<br>
<a href="https://security.googleblog.com/2017/05/oss-fuzz-five-months-later-and.html">https://security.googleblog.com/2017/05/oss-fuzz-five-months-later-and.html</a><br>
[18] <a href="https://www.atlassian.com/software/views/open-source-license-request">https://www.atlassian.com/software/views/open-source-license-request</a></p>

