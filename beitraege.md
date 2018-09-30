Beiträge zu FLOSS-Projekten
===========================

*[Zur Startseite](./)*

- [22. Juni: Yarn *(kkuhr)*](https://github.com/yarnpkg/yarn)
- [22. Juni: Mark Text *(mklpiening)*](https://github.com/marktext/marktext)
- [22. Juni: Shairport-Sync *(tillz)*](https://github.com/mikebrady/shairport-sync)
Das Projekt ist eine freie Implementierung des Airplay-Protokolls. Airplay dient Apple-Geräten dazu,
Audio-Streams über das Netzwerk auf einem Abspielgerät auszugeben. Shairport-Sync implementiert hier
die Empfänger-Funktionalität. Diese Software empfängt also von Apple-Geräten Audio-Streams, und gibt diese
lokal wieder.
Gleichzeitig sieht das Protokoll vor, das der Sender des Streams einen Webserver zur Verfügung stellt,
über den die Wiedergabe gesteuert werden kann. Zusammen mit anderen Metadaten (Lautstärke, aktueller Titel) werden
auch die Parameter dieses Webservers (Port, Zugangscode) über das Airplay-Protokoll an den Empfänger übermittelt,
sodass dieser bspw. den Titel anzeigen kann.
Der Beitrag bestand in der Erweiterung der Software "Shairport" um einen MQTT-Client,
sodass Metadaten, welche im Protokoll mit übermittelt werden an einen MQTT-Broker weitergeleitet werden.
Außerdem ist es möglich, die Wiedergabe auf dem Sende-Gerät via MQTT zu steuern, bspw. die Lautstärke zu verändern
oder die Wiedergabe zu pausieren.
Der Beitrag war technisch recht anspruchsvoll, u.A. aufgrund des nicht ganz einfachen Build-Systems sowie der
verwendeten Sprache (C).
Nachdem die Erweiterung durchgeführt wurde, wurde ein Pull-Request gestellt, welcher nach kurzer Rückfrage problemlos
übernommen wurde - jedoch vorerst nur im Development-Branch.
- [22. Juni: Ubuntu Touch *(rmirau)*](#)
- [22. Juni: coala *(dkopatz)*](#)
- [29. Juni: Angular 6 Tutorial *fistutzenste*](#)
- [29. Juni: Rust *(KarolinePlum)*](https://github.com/rust-lang/)
Bezüglich des Projektes siehe [Projektvorstellung](projekte.md). Ich habe durch eine kleine Änderung in der Dokumentation von Rust ([Issue](https://github.com/rust-lang/rust/issues/52263)) und bei der Übersetzung von insgesamt ca. einem Kapitel des [Rust-Buches](https://github.com/rust-lang/book/issues) ([Issue](https://github.com/rust-lang/book/issues/1386)) beigetragen.  
- [29. Juni: *ashek*](#)
- [29. Juni: Zim *(astiefvater)*](#)
- [29. Juni: rambox *(pluettmann)*](#)
- [29. Juni: (ekeser)](#)
- [29. Juni: mas *(ottker)*](https://github.com/mas-cli/mas)
