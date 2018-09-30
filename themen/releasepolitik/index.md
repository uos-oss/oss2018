Releasepolitik und Versionsnummern
=================================================
*[Zur Themenübersicht](../../themen.md)*

Inhalt
------
1. [Einleitung](#einleitung)
2. [Releasezeitplan](#releasezeitplan)
3. [Vorbereitung des Codes für das Release](#vorbereitung-des-codes-für-das-release)
4. [Versionsnamen](#versionsnamen)

Einleitung
----------

Wenn man an einem Softwareprojekt arbeitet, ist es oft das Ziel, zu einem gewissen Zeitpunkt den Projektcode in einen konsistenten und in sich geschlossenen, möglichst fehlerfreien Zustand zu bringen, um ihn dann an potentielle Nutzer ausliefern zu können. Damit verbunden sind die Begriffe Release und Version, die oft austauschbar verwendet werden können. Der Begriff Release legt dabei den Fokus eher auf den Prozess der Auslieferung an die Nutzer, während eine Version eher mit dem internen Zustand des Codes in Verbindung gebracht wird.

Es gibt auch viele Projekte (besonders in der FLOSS-Welt), die keine expliziten Releases vornehmen, sondern versuchen, die Codebasis zu jedem Zeitpunkt möglichst konsistent und sinnvoll zu halten, sodass User jederzeit den aktuellen Zustand abgreifen und ihn auch sinnvoll benutzen können (*rolling / no release*). In dieser Ausarbeitung soll es allerdings um Projekte gehen, die einen richtigen Releasezyklus besitzen, wo also das Release eine besondere Version der Software ist, auf die explizit hingearbeitet wird.

In dieser Ausarbeitung sollen drei Aspekte betrachtet werden, die für Releases wichtig sind. Zunächst einmal sollte für das Projekt entschieden werden, wann das nächste Release anstehen soll und eventuell auch ein Plan für darauffolgende Releases. Dann muss strukturiert werden, wie das Team zusammen vorgeht, um einen releasebereiten Code zu erarbeiten. Schließlich sollte dem Release auch ein Name zugeteilt werden, der es sinnvoll in der Versionshistorie identifiziert.

Releasezeitplan
---------------

Es existieren zwei grundlegende Ansätze bei der Erstellung eines Zeitplans für Releases: der featurebasierte und der zeitbasierte Ansatz. Beim traditionelleren featurebasierten Ansatz wird festgelegt, welche Features mit dem nächsten Release ausgeliefert werden sollen, und der Releasezeitpunkt wird dementsprechend angepasst. Beim moderneren zeitbasiertem Ansatz wird hingegen ein zeitlich festgelegter Releasezyklus gewählt (z.B. Release alle 6 Wochen), und alle Features, die zum Releasezeitpunkt fertig sind, werden in das Release mit aufgenommen, an dem Rest wird für spätere Releases weitergearbeitet.

Im Folgenden werden einige Vor- und Nachteile betrachtet, die die jeweiligen Ansätze mit sich bringen und es wird insbesondere auf die speziellen Anforderungen bei FLOSS-Projekten eingegangen.

#### Featurebasierter Ansatz
Featurebasierte Releases haben den Vorteil, dass sie - wenn sie funktionieren - marketingtechnisch wirkungsvoll sind und aufeinander abgestimmte Features bieten. Allerdings ist es schwierig, abzuschätzen, wann bestimmte Features fertig werden und dementsprechend zu planen, Verzögerungen können Druck erzeugen. Desweiteren kann argumentiert werden, dass Features nie wirklich fertig sind und es immer Raum für Verbesserung gibt.

#### Zeitbasierter Ansatz
Zeitbasierte Releases haben den Vorteil, dass durch einen von Release zu Release gleichen Zeitplan eine Routine entsteht. Durch diese Routine kann der Bedarf nach Intervention und Koordination von Außen verringert werden und Projektteilnehmer können durch die Routine ihre Aufgaben eingespielter lösen und adäquate Erwartungen entwickeln. Außerdem kann die Routine motivierend für die Teammitglieder wirken.

Durch den festen Releasezyklus können außerdem Vorteile für die Repräsentation des Projektes gegenüber Nutzern entstehen. Die stetigen Releases können Nutzern signalisieren, dass sich das Projekt in einem gesunden Zustand befindet, gut organisiert ist und voraussichtlich in der Zukunft noch weiter Support erhalten wird.

Darüber hinaus können Nutzer sich den zeitlichen Releaserhytmus merken und erwarten daher ein Release und schauen sich möglicherweise sogar von selbst aus das neue Release an, ohne eine Benachrichtigung irgendeiner Art über das Release erhalten haben zu müssen. Dieser Aspekt kann insbesondere bei verteilter Software relevant werden, wo sich Nutzer aktiv das neue Release installieren müssen, um davon zu profitieren. Selbst bei *Software as a Service* kann es aber von Vorteil sein, wenn sich die Nutzer auf den Releasezeitpunkt einstellen können, zum Beispiel um sich über das neue Release zu informieren und eventuell Auswirkungen auf das eigene Projekt einzuschätzen.

Jedoch sind zeitbasierte Releases natürlich nur sinnvoll bei größeren Projekten, wo genügend daran gearbeitet wird, um stetig neue Releases zu erlauben.
#### Zur Länge des Releasezyklus
Sowohl zeitbasierte als auch featurebasierte Ansätze können kurze oder lange Releasezyklen haben, auch wenn Projekte mit zeitbasierten Releases öfter releasen, d.h. kürzere Releasezyklen haben.

Ein verbreites Motto in der FLOSS-Welt:
> Release early, release often. ([Eric S. Raymond, The Cathedral and the Bazaar](http://www.catb.org/esr/writings/cathedral-bazaar/cathedral-bazaar/ar01s04.html))

##### Mögliche Vorteile kürzerer Releasezyklen
- Schnelleres Feedback von Nutzern
- Motivation der Projektteilnehmer durch schnelleres "Früchte-Tragen" der Arbeit
- Häufiges Synchronisieren des Codes, Arbeiten driften nicht auseinander
- Projekt eher auf aktuellem Stand
##### Mögliche Nachteile kürzerer Releasezyklen
- Fragmentierung der Userbasis
- Überforderung von Nutzern
- weniger geeignet für radikale Umstrukturierungen am gesamten Projekt
- eventuelle Fixkosten für jedes einzelne Release (immer weniger relevant durch Automatisierung von immer mehr Prozessen)

#### Besondere Anforderungen von FLOSS
Auf Grund von häufigen Anforderungen und Einschränkungen von FLOSS-Projekten kann argumentiert werden, dass zeitbasierte Releases mit kürzeren Releasezyklen tendenziell geeigneter für diese Projekte sind.

Eine Besonderheit im Vergleich zu traditioneller Softwareentwicklung in einer Firma ist die häufige räumliche und zeitliche Trennung der Projektteilnehmer, wodurch Kommunikation und Koordination erschwert werden. Da beim zeitbasierten Ansatz der Ablauf mehr oder weniger von vorneherein geregelt ist, profitieren alle Teilnehmer davon dass durch die Eingespieltheit weniger Koordination und Kommunikation nötig wird.
Außerdem ist die Arbeit an FLOSS-Projekten oft (nicht immer) eine freiwillige Arbeit, was bedeutet, dass die Motivation der Teilnehmer umso wichtiger wird, die durch die regelmäßige Veröffentlichung der eigenen Leistungen erreicht werden kann.

Auch kann es manchmal sein, dass potentielle Nutzer FLOSS-Projekten weniger vertrauen als proprietären Projekten, vielleicht weil sie keine Sicherheit für weitere Arbeit am Projekt verspüren, von daher können stetige Releases als eine Art "Puls" des Projektes besonders wichtig sein, um diese Nutzer von der Professionalität und Gesundheit des Projektes zu überzeugen.

Schließlich fällt ein großer Anreiz von featurebasierten Releases bei FLOSS-Projekten häufig weg. Denn sie sind oft nichtkommerziell und haben große, marketingtechnisch beeindruckende sogenannte "Big-Bang Releases" weniger nötig.

#### Quellen:
- ["Why we shift objectives and not release dates at GitLab"](https://about.gitlab.com/2015/12/07/why-we-shift-objectives-and-not-release-dates-at-gitlab/)
- [Martin Milchmayr (2007): “Quality Improvement in Volunteer Free and Open Source Software Projects”](cyrius.com/publications/michlmayr-phd.pdf)

Vorbereitung des Codes für das Release
--------------------------------------
Die Arbeit an einem komplexen Projekt mit mehreren Projektteilnehmern erfordert Strukturierung, damit ein releasefertiger Code erarbeitet werden kann. Dabei gibt es unzählige Methoden, die eingesetzt werden können, wie z.B. Peer-Review, Continuos Integration, Code-Freezes, Feature-Freezes, String-Freezes, Merge-Windows, und diverse Branchingmodelle für git. An dieser Stelle wird ein Branchingmodell exemplarisch vorgestellt.
#### gitflow
[Gitflow](https://nvie.com/posts/a-successful-git-branching-model/) ist ein verbreites Branchingmodell, das dabei hilft, die Arbeit an Projekten mit komplexeren Releasezyklen zu strukturieren.
[![Grafik für gitflow](https://nvie.com/img/git-model@2x.png "Grafik von Vincent Driessen, Lizenz: Creative Commons BY-SA")](https://nvie.com/posts/a-successful-git-branching-model/)
- Es gibt zwei ständige Branches, *merge* und *develop*, und beliebig viele temporäre Branches.
- Wenn ein neues Feature beigetragen werden soll, wird ein neuer, von *develop* abzweigender *feature* Branch dafür erstellt und die Entwicklung auf diesem betrieben.
- Sobald die Entwicklung für das Feature abgeschlossen ist, und das feature in das nächste von *develop* abzweigende Release aufgenommen werden soll, wird der *feature* Branch in develop gemerget und wieder geschlossen.
- Wenn ein neues Release ansteht, wird ein neuer von *develop* abzweigender *release* Branch erstellt, auf dem keine neuen Features mehr hinzugefügt werden, sondern nur noch Vorbereitungen, Tests und Fehlerbehebungen für das neue Release getätigt werden.
- Zum Release wird der *release* Branch wieder geschlossen und sowohl in *master* also auch in *develop* gemerget.
- Wenn im Release Fehler gefunden wurden, die dringend behoben werden müssen, wird direkt von *master* ein *hotfix* Branch abgezweigt, auf dem der Fehler unabhängig von eventuell neuen Entwicklungen auf dem *develop* Branches möglichst schnell behoben werden kann.

Dieses Modell erscheint wohl auf den ersten und zweiten Blick unnötig komplex, ist aber meiner Meinung nach nötig, wenn ein Feature-Freeze für das neue Release mit gleichzeitiger Weiterentwicklung an der Codebasis des Projektes erwünscht bzw. nötig ist.

#### Weitere Branchingmodelle
- [GitHub Flow](https://guides.github.com/introduction/flow/): sehr leichtgewichtig, typischer Workflow auf GitHub
- [GitLab Flow](https://docs.gitlab.com/ee/workflow/gitlab_flow.html): komplexer als GitHub Flow, aber weniger komplex als gitflow

#### Weitere Quelle
- ["GitFlow vs GitHubFlow"](https://www.freshconsulting.com/git-development-workflows-git-flow-vs-github-flow/)

Versionsnamen
-------------
Die Benennung eines Releases (auch Versionierung genannt) sollte möglichst konsistent und sinnvoll erfolgen, ohne zu kompliziert zu werden. An Hand des Versionsnames sollte der Nutzer die Version eindeutig identifizieren können und alleinstehend oder im Vergleich mit anderen Versionsnamen Informationen extrahieren können. Allerdings gehören zu jedem Release zusätzlich Releasenotes, die den Inhalt und die Änderungen in diesem Release ganz genau spezifizieren. Semantic Versioning ist die zur Zeit am weitesten Verbreiteste Vorgehensweise zur Benennung von Softwareversionen.
#### Semantic Versioning
Alle Projekte, die eine öffentliche API besitzen, können mit Hilfe von Semantic Versioning ihre Versionen so benennen, dass Nutzer an Hand des Versionsnamen sinnvolle Rückschlüsse auf die  Konsequenzen, die ein Upgrade auf eine neue Version mit sich bringen könnte, ziehen können. Die Benennung erfolgt wie folgt:

- Jeder Versionsname besteht mindestens aus dem Dreitupel **Major.Minor.Patch**, wobei Major-, Minor- und Patchnummer jeweils ganze Zahlen sind.
- Die Versionshistorie startet bei **0.0.0**.
- Bei Änderungen von einer zur nächsten Version, die **keine Auswirkungen auf die öffentliche API** mit sich bringen, wie z.B kleinen Fehlerbehebungen, wird **Patch** inkrementiert.
- Bei Änderungen, die (auch) **rückwärtskompatible Änderungen der API** enthalten, wie z.B. das Hinzufügen von neuen Features, wird **Minor** inkrementiert und Patch zurückgesetzt.
- Bei Änderungen, die (auch) Änderungen enthalten, die die in der API der Vorgängerversion getroffenen Absprachen bzw. Verträge verletzen (**breaking changes**), wird **Major** inkrementiert und Minor und Patch zurückgesetzt.
- Ausnahme: solange die Majornummer 0 ist, wird Minor wie Major behandelt und Patch wie Minor. Dies ist für die initiale Entwicklungsphase gedacht, zu diesem Zeitpunkt sollte die öffentliche API als instabil angesehen werden.
- Optional hinter Major.Minor.Patch können noch der Name des Pre-release und Metadaten über den Build angegeben werden, für Details siehe [SemVer-Spezifikation](https://semver.org/).

Durch Vergleichen der alten mit der neuen  Versionsnummer können Nutzer also auf den ersten Blick besser einschätzen, ob durch ein Upgrade einer Dependency Änderungen am eigenen Projekt notwendig werden würden, um wieder die gewünschte Funktionalität herzustellen. Es können z.B. auch Paketmanager verwendet werden, um an Hand der Versionsnummer automatische Upgrades auf neue Versionen durchzuführen, die keine *breaking changes* enthalten. Dies wird immer wichtiger, gerade in der FLOSS-Welt, da auf möglichst modulare Software gesetzt wird und es tendenziell immer mehr Dependencies gibt.

Außerdem können durch Semantic Versioning Nutzer dazu angehalten werden, ihr Projekt besser zu strukturieren, weil möglichst vermieden werden will, andauernd die Majornummer zu erhöhen. Denn wenn Nutzer sehen, dass eine neue *major version* releast wurde, kann die Erwartung entstehen, dass diese neue Version grundlegende neue Features und Verbesserungen mit sich bringt und nicht nur minimale rückwärtsinkompatible Änderungen an der API auf Grund von schlechter Vorausplanung des Projektes. Natürlich steht das nicht in der Spezifikation von Semantic Versioning, aber der Name *Major* und der Fakt, dass jede minimale Änderungen der API direkt offensichtlich sichtbar gemacht werden muss, können dazu beitragen, dass das Projekt sich genauer überlegt, wann *breaking changes* wirklich nötig sind.

Allerdings ist vollkommener Verlass auf diese Versionsnummern offensichtlich nicht angebracht: Es kann sein, dass *breaking changes* übersehen wurden, oder auch dass die Majornummer auf Grund von überhöhter Vorsicht, Unsicherheit oder Missachtung erhöht wurde, obwohl gar kein *breaking change* vorliegt. Desweiteren besteht die Möglicheit, dass eine Nummer nach dem Schema *X.Y.Z* zwar nach Semantic Versioning aussieht, der Spezifikation aber gar nicht folgt, siehe Sentimental Versioning im folgenden Abschnitt.

#### Weitere Versionierungspraktiken
- ***Sentimental*** oder auch ***Romantic Versioning***: sieht nach Semantic Versioning aus, ist es aber nicht, da das Projekt selbst entscheidet, was ein *major* und was ein *minor change* ist, da Semantic Versioning als unzulänglich angesehen wird (siehe Diskussion. [hier](https://gist.github.com/jashkenas/cbd2b088e20279ae2c8e))
- ***Releasedatum als Versionsname***: Nutzer können an Hand von Versionsnamen direkt erkennen, wie aktuell ihre Version ist.
- ***Spitz- bzw. Codenamen*** für Release: oft parallel zu anderem Versionsnamen.
- ***Long Term Support-Tags***: Anzeige im Namen, wie lange Version veraussichtlich unterstützt wird.

#### Weitere Quellen:
- [Wikipediaeintrag zu Software Versioning](en.wikipedia.org/wiki/Software_versioning)
- [Blogeintrag "Sentimental Versioning"](http://sentimentalversioning.org/)
