Ein Überblick über Code- und Versionsverwaltungssysteme
=================================================
*[Zur Themenübersicht](../../themen.md)*

Inhalt
------
1. [Einleitung](#einleitung)
2. [Zielgruppe von Versionsverwaltungssystemen](#zielgruppe)
3. [Grundlegende Strukturen von VCS](#strukturen)
4. [Speicherung der Versionen](#speicherung)
5. [Vorstellung einiger Versionsverwaltungssysteme](#vorstellung)
6. [Fazit](#fazit)

Einleitung
----------

Versionsverwaltungssysteme (kurz VCS) sind Systeme, die Änderungen in Dateien ablegt, um es zu ermöglichen, später zu einem älteren Zustand zurückzukehren. ([Git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control))
Das bedeutet insbesondere, dass Fehler rückgängig gemacht werden können während Mitarbeiter zeitgleich ungestört weiterarbeiten. ([Atlassian](https://www.atlassian.com/git/tutorials/what-is-version-control))

Jeder hat vermutlich schon einmal mit solch einem Versionsverwaltungssystem zu tun gehabt oder gearbeitet. Dabei stellt sich beim Starten eines neuen Projekts  häufig die Frage, welches Versionsverwaltingssystem für das Projekt genutzt werden soll. Oft wird bei auf diese Frage mit dem System namens Git geantwortet, da dies das am weitesten verbreitete und am meisten verwendete Versionsverwaltungssystem ist. Es existieren somit auch sehr viele online Services, die einen hosting Service von Online Git Repositories zur Verfügung stellen. Eines dieser Systeme ist Github. Github biete die Möglichkeit kostenlos öffentliche Git Repositorys zu erstellen, die genutzt werden können, um den eigenen Code zu verwalten. Somit ist Github eine der größten Plattformen für open source Software. Ähnlich sieht es bei anderen Anbietern solcher Services, wie GitLab aus. Auch die Verteilung von freier Software werden häufig solche Services verwendet. Versionsverwaltungssysteme scheinen also nicht unbedeutend für die Existenz von Open Source Projekten zu sein.

Um die Frage darüber, welches Versionsverwaltungssystem für eigene Projekte zu empfehlen ist, etwas differenzierter als nur mit "Git" beantworten zu können und ein Verständnis über die Vor- und Nachteile der verschiedenen Versionsverwaltungssysteme zu schaffen, soll diese Arbeit einen kleinen Überblick über die verschiedenen Versionsverwaltungssysteme inklusive deren Stärken und Schwächen geben.

Zielgruppe von Versionsverwaltungssystemen
------------------------------------------

Auf Versionsverwaltungssysteme stößt man zwar besonders häufig in der Softwareentwicklung, aber auch in anderen Bereichen ergibt ein Einsatz solcher Systeme Sinn. Ein Beispiel wäre die Hardwareentwicklung. Dort gibt es viele Ansätze auch Versionsverwaltungssysteme zu nutzen, die ursprünglich für die Softwareentwicklung entworfen wurden. ([ERPNext](https://discuss.erpnext.com/t/erpnext-git-github-for-open-source-hardware-call-for-beta-user-s/18006)) Auch für Webdesigner und alle Anderen, die mit sich ändernden Dateien arbeiten, ist der Einsatz von Versionsverwaltungssystemen sinnvoll und vereinfacht die Arbeit an vielen Stellen. ([Atlassian](https://www.atlassian.com/git/tutorials/what-is-version-control))

In dieser Arbeit werde ich jedoch besonder auf die Sicht der Programmierung eingehen, da es für das Thema der Open Source Software am interessantesten ist. Die Versionsverwaltungssysteme, die ich in dieser Arbeit beschreiben werde, verwalten also Source Code und werden somit auch Codeverwaltungssysteme genannt.

Grundlegende Strukturen von VCS
-------------------------------

Um den Vergleich zwischen Versionsverwaltungssystemen zu ermöglichen, werden Informationen über die interne Struktur solcher Systeme benötigt, da aus der internen Struktur auch direkt Ideen und Ansätze für die Schnittstelle des jeweiligen Systems folgen. Außerdem sind die internen Strukturen nicht unwichtig für den Workflow, den diese Versionsverwaltungssysteme haben.

Grundsätzlich existieren drei Aufbauten von Versionsverwaltungssystemen. Dazu gehört der lokale, der zentralisierte und der verteilte Ansatz des Aufbaus.

Beim lokalen Ansatz handelt es sich um den einfachsten der drei Ansätze. Er basiert darauf, dass alle Änderungen lokal abgelegt und verwaltet werden. ([Git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)) Dies ist in dieser Abbildung vereinfacht veranschaulicht:

<img src="img/vcs_local.png" height="300">

Versionen beschreiben hierbei Zustände der versionierten Datei, auf die die aktuelle Datei zurückgesetzt werden kann. In diesem Diagramm kann man sehr gut erkennen, dass alle Versionen lokal auf dem Rechner abgelegt sind und die aktuell genutzte Datei auf einer Version aus der Datenbank basiert. ([Git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)) Nachteile hierbei sind zum Beispiel, dass Änderungen nicht mit anderen Nutzern synchronisiert werden, sodass ein Arbeiten im Team mit diesem Ansatz nicht besonders angenehm sein kann. Auch besteht das Problem, dass bei einem Defekt des Datenspeichers des Rechners direkt alle Daten und Versionen verloren sind. Eine Lösung für dieses Problem wären Backups, welche jedoch gegen den Sinn eines Versionsverwaltungssystems stehen.

Der zentrale Ansatz versucht, das Problem der Zusammenarbeit zu beheben und damit eine solche Zusammenarbeit am selben Projekt problemlos und möglichst konfliktfrei zu ermöglichen. Dabei werden alle Versionen auf den Server ausgelagert. Die aktuell bearbeiteten Dateien liegen bei den Clients, verweisen aber auf die Version, auf der sie basieren, welche auf dem Server liegt. ([Git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)) Die folgende Abbildung stellt diesen Aufbau vereinfacht dar:

<img src="img/vcs_central.png" height="300">

Ein Nachteil dieses Ansatzes ist, dass das offline Arbeiten insofern nicht möglich ist, dass offline keine neuen Versionspunkte erstellt werden können. Außerdem besteht auch hier noch das bereits genannte Problem der Datenverluste durch Defekte des Rechners, der die Versionen hält.

Die dritte und damit letzte Möglichkeit, ein Versionsverwaltungssystem zu modellieren, die ich vorstelle, versucht die Vorteile des zentralen Ansatzes auszunutzen und gleichzeitig die negativen Punkte zu verbessern. Dieser Ansatz ist der dezentrale Ansatz.

Bei diesem Ansatz liegen alle Versionen sowohl bei den Clients, als auch auf den Servern. Die lokalen Arbeitskopien sind nur auf den Clients vorhanden und verweisen auf die Version des Clients, auf der sie basieren. Zudem werden Versionen zwischen Server und Clients synchronisiert. Auch die Synchronisierung direkt unter den Clients ist möglich. ([Git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control))

<img src="img/vcs_decentral.png" height="350">

Durch diese Struktur wird es möglich, offline neue Versionen zu erstellen und auch auf ältere Versionen zuzugreifen. ([Git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)) Die Synchronisierung ist weiterhin nur online möglich. Auch das Problem der Datenverluste wird durch dieses System behoben, da beim Datenverlust eines Teilnehmers dieses Systems die Daten mit einem anderen Teilenhmer wieder synchronisiert werden können, wodurch die Daten in den meisten Fällen wiederhergestellt werden können.

Speicherung der Versionen
-------------------------

In der letzten Sektion war wiederholt die Rede von Versionen. Dabei stellt sich die Frage, wie solche Versionen auf dem Rechner dargestellt und abgespeichert werden.

Auch hierbei gibt es verschiedene Ansätze, welche einmal die Deltas und einmal die Snapshots sind.
Die Deltas lassen sich dabei weiter in Vorwärts- und Rückwärtsdeltas aufteilen. 

Bei Vorwärtsdeltas ist die zuerst erstellte Version einer Datei vollständig abgespeichtert. Alle darauffolgenden Versionen sind nur als meist zeilenweise Unterschiede zu ihrem Vorgängerzustand abgelegt. Dadurch wird der Zugriff auf ältere Versionen schneller und der Zugriff auf neuere Zustände verzögert sich. ([Git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics))
Die folgende Abbildung zeigt einen solchen Aufbau. Dabei ist das grün markierte Element komplett abgespeichert und die grauen Elemente sind Deltas.

<img src="img/forward_delta.png" height="200">

Rückwärtsdeltas arbeiten genau in die entgegengesetzte Richtung. Bei ihnen ist der neuste Zustand komplett abgespeichert und alle Vorgängerversionen sind mit Unterschieden zu ihrer Nachfolgerversion versehen. Das führt zu einem schnellen Zugriff auf die neueren Versionen und einem umso Langsameren auf die älteren Versionen. 
Diese Abbildung zeigt reverse Deltas:

<img src="img/reverse_delta.png" height="200">

Welcher der beiden Deltas nun besser ist, kommt ganz auf den Anwendungsfall an. In den meisten Fällen wird jedoch ein Zugriff auf die neueren Versionen häufiger vorkommen als ein Zugriff auf die älteren Versionen, weshalb meistens die Rückwärtsdeltas zu empfehlen sind.

Ein Nachteil dieser Delta Repräsentation ist jedoch, dass für den Fall eines Datenverlusts in einer Version alle Versionen, die von dieser fehlerhaften Version ableiten, ebenfalls fehlerhaft sind. Es existieren jedoch Ansätze und Implementationen, die dieses Problem weniger kritisch machen.

Als Alternative zu den Deltas existiert auch die Versionssicherung durch Snapshots. Hierbei wird jede Version einzeln abgespeichert, oder die vorherige Version referenziert, falls es keine Änderungen in der jeweiligen Datei gab. Im Fall einer Referenzierung wird nicht wieder die gesammte Datei abgespeichert, sondern nur eine Referenz auf die letzte Version der jeweiligen Datei. ([Git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics))
Die folgende Abbildung stellt diese Snapshots dar. Dabei sind grau markierte Elemente referenzierte Versionen und grün markierte Elemente als Snapshot ablegt. Die Version 0 ist die erste Version und die Version 2 die Aktuellste.

<img src="img/snapshot.png" height="200">

Vorteile dieser Repräsentation sind z.B. die hohe Geschwindigkeit beim Zurücksetzen und die Sicherheit vor Fehlern in einer Version. Tritt nämlich ein Datenverlust in einer Version auf, ist nur diese Version und gegebenenfalls die diese Version referenzierenden Versionen betroffen. ([Git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)) Ein großer Nachteil ist aber die der Speicherverbrauch, welcher um einiges größer ausfällt als bei Deltas.

Vorstellung einiger Versionsverwaltungssysteme
----------------------------------------------

Nachdem nun die Grundlagen der Versionsverwaltungssysteme vorgestellt wurden, werden nun einige Versionsverwaltungssysteme in chronologischer Reihenfolge vorgestellt, um sowohl die Optimierung der Systeme, als auch die gleich bleibenden Ansätze im Design der Systeme klar zu machen.

Bereits 1972 wurde das SCCS von Marc J. Rochkind veröffentlicht. Dieses System ist auf die Operationen des Erstellens und Zurücksetzens von Versionen beschränkt und folgt dem lokalen Ansatz, ist also nicht für die Zusammenarbeit in Teams entworfen. ([opengroup](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/get.html)) Außerdem werden nur einzelne Dateien verwaltet, weshalb sich auch der Einsatz von SCCS in Projekten schwierig gestaltet. Zum Ablegen der Versionen sind Rückwärtsdeltas verwendet. Das Problem des Datenverlusts und der Fortsetzung der entstandenen Fehler im Versionsverlauf ist jedoch durch Checksummen, die in der sogenannten HistoryFile abgelegt sind, eingeschränkt. ([gnu.org](https://www.gnu.org/software/rcs/tichy-paper.pdf)) Lizensiert ist dieses Open Source Versionsverwaltungssystem mit einer eigenen Lizenz, wird jedoch heutzutage kaum noch produktiv eingesetzt.

Im Jahr 1990 wurde das Versionsverwaltungssystem ClearCase veröffentlicht, welches noch heute eigesetzt wird. Enwtickelt wurde es von David Leblang und Howard Spilke, wurde jedoch mehrfach verkauft und ist heute im Besitz von IBM. Das System arbeitet Zentralisiert und nutzt Rückwärtsdeltas, wodurch es für den produktiven Einsatz in Teams geeignet ist. ([IBM](https://www.ibm.com/support/knowledgecenter/en/SSSH27_9.0.1/com.ibm.rational.clearcase.cc_admin.doc/topics/c_intro_hostadmin_data_rgy.htm)) Zudem sind die Rückwärtsdeltas direkt in den Dateien selber abgelegt, wodurch der Zugriff auch bei älteren Versionen schnell abläuft. Dieses Deltas werden interleaved Deltas genannt. Die Deltas sind genau wie alle anderen relevanten Versionsverwaltungssysteme mit Deltas mit Checksummen versehen, wodurch die Fehleranfälligkeit sinkt. ([IBM](https://www.redbooks.ibm.com/redbooks/pdfs/sg246399.pdf)) ClearCase ist proprietär und die Struktur ist sehr komplex gestaltet, weshalb das Aufsetzen eines solchen ClearCase Services viel Zeit in Anspruch nimmt.

Ein weiteres, heute noch intensiv genutztes Versionsverwaltungssystem mit den Namen Subversion (kurz SVN) wurde 2000 veröffentlicht. ([apache](https://subversion.apache.org/)) Subversion ist ein open Source Projekt, welches nach der Apache 2.0 Lizenz lizensiert ist. Es arbeitet genau wie ClearCase zentralisiert und nutzt ebenfalls Rückwärtsdeltas. ([red bean](http://svnbook.red-bean.com/)) Wie auch schon bei ClearCase ist das Arbeiten mit der Versionsverwaltung nur Online möglich, da die Versionen durch den zentralisierten Aufbau nur auf dem Server abgelegt sind. Eine Besonderheit von SVN ist das Sperren von Versionen. In SVN kann also eine Version so gesperrt werden, dass niemand mehr auf Grundlage der gesperrten Version eine neue Version erstellen darf. Dadurch kann gewährleistet werden, dass keine Konflikte mit den eigenen Änderungen entstehen. ([tortoisesvn](https://tortoisesvn.net/docs/release/TortoiseSVN_en/tsvn-dug-locking.html)) Subversion unterstützt kein explizites Branching. Das heißt, das Aufteilen des Projekts, um mehreren Entwicklern zu ermöglichen, parallel am selben Projekt an unterschiedlichen Aufgaben zu arbeiten ist nur über einen Umweg möglich. Dieser Umweg ist das Kopieren des gesammten Projekts. ([red bean](http://svnbook.red-bean.com/)) Ein Zusammenfügen der verschiedenen Branches, das sogenannte Merging, wird jedoch direkt von Subversion unterstützt.

Das nächste Versionsverwaltungssystem ist das bereits in der Einleitung angesprochene Git. Es wurde 2005 unter der gnu gpl v2 open Source Lizenz veröffentlicht. Die Entwicklung von Git begann mit dem Ziel, Git als neues Versionsverwaltungssystem für das Projekt zum Linux Kernel zu verwenden, nachdem das vorher verwendete Versionsverwaltungssystem BitKeeper, welches 2000 veröffentlicht wurde und auf den Schnittstellen des anfangs erwähnten SCCS basiert, seine freie Lizenz entfernte. ([Git](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git)) Deshalb orientiert sich der Workflow von Git stark an dem Workflow von BitKeeper. Wie bereits anfänglich genannt ist Git das am weitesten verbreitete Versionsverwaltungssystem für Softwareprojekte. Git ist ein verteiltes System und speichert die Versionen in Snapshots, ermöglicht also das Zusammenarbeiten in Teams und das offline Arbeiten. Es ist also möglich,  offline neue Versionen erstellt und auf alte Versionen zurückzugehen. Um dem großen Speichergebrauch der Snapshot Repräsentation für die Versionen entgegenzuwirken, nutzt Git eine verlustfreie Komprimierung. Außerdem unterstützt Git nativ das Branching und Merging von Branches. ([Git](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell))

Mercurial ist genau wie Git ein Versionsverwaltungssystem, welches dazu entwickelt wurde, um BitKeeper beim Linux Kernel Projekt zu ersetzen und wurde ebenfalls 2005 unter der gnu gpl v2 open Source Lizenz von Matt Mackall veröffentlicht. ([Mercurial](https://www.mercurial-scm.org/about)) Mercurial verlor jedoch die Wahl des nächsten Versionsverwaltungssystems für das Linux Projekt gegen Git. Genau wie Git ist Mercurial verteilt und hat eine sehr ähnliche Schnittstelle. Mercurial nutzt aber für die Versionen sowohl Snapshots, als auch Forward Deltas. Dabei wird nach einer bestimmten Anzahl von Deltas ein Snapshot erstellt. Dadurch sinkt sowohl die Zugriffszeit im Gegensatz zu reinen Delta Repräsentationen, als auch der Speicherverbrauch im Gegensatz zu reinen Snapshot Repräsentationen. ([red bean](http://hgbook.red-bean.com/read/behind-the-scenes.html)) Mercurial wird heutzutage noch sehr häufig, aber seltener als Git eingesetzt.

Das letzte Versionsverwaltungssysten, das hier vorgestellt wird, ist der Team Foundation Server, welcher 2006 von Microsoft veröffentlicht wurde. Der Team Foundation Server besteht nicht nur aus einer Versionsverwaltung, sondern beinhaltet auch viele Tools für Entwicklerteams. Dazu gehören zum Beispiel Scrum Product Backlogs oder grafische Oberflächen. ([Microsoft](https://visualstudio.microsoft.com/de/tfs/)) Das System ist proprietär, arbeitet zentralisiert und nutzt bei den Versionen Rückwärtsdeltas. ([Microsoft](https://blogs.msdn.microsoft.com/billheys/2011/05/05/how-tfs-stores-files-and-calculated-deltas-on-versioned-files/)) Mittlerweile hat sich Microsoft mit dem Team Foundation Server etwas vom eigenen Versioneverwaltungssystem entfernt und stattdessen einen Git Service eingebaut. ([Microsoft](https://docs.microsoft.com/de-de/vsts/repos/git/overview?view=vsts))

Fazit
-----

Abschließend stellt sich nun die Frage, welches Versionsverwaltungssystem nun das optimale ist. Als Antwort kann man nur sagen, dass es ganz auf den Anwendungsfall ankommt. Fragen wie "Arbeitet man allein?", "Benötigt man einen schnellen Zugriff auf ältere Versionen?", "Ist der Speicherbedarf unwichtig?" und viele weitere müssen beantwortet werden, um das optimale Versionsverwaltungssystem für den eigenen Anwendungsfall zu finden, aber für die meisten Anwendungsfälle ist das offline Arbeiten und die Möglichkeit der Zusammenarbeit mit Anderen nicht uninteressant. Außerdem hilft eine Branching Unterstützung auch bei Parallelem Arbeiten an verschieden Aufgaben bei nur einem Entwickler oft weiter und vereinfacht die Planung und Verwaltung des Projekts. Aus diesen Gründen kann man sagen, dass für die meisten Anwendungsfälle ein Versionsverwaltungssystem wie Git, oder Mercurial den Anforderungen besser gerecht wird als andere Versionsverwaltungssysteme.