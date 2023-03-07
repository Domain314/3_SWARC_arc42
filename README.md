# SAWRC_arc42
Software Architecture - arc42 filled out (German)

### MasterPW NG

## Über arc42

arc42, das Template zur Dokumentation von Software- und Systemarchitekturen.
Erstellt von Dr. Gernot Starke, Dr. Peter Hruschka und Mitwirkenden.
Template Revision: 7.0 DE (asciidoc-based), January 2017
© We acknowledge that this document uses material from the arc42 architecture template,
http://www.arc42.de. Created by Dr. Peter Hruschka & Dr. Gernot Starke.


## Einführung und Ziele

Durch den massiven Erfolg des Vorgängers MasterPW® steht dem nächsten logischen
Schritt nichts im Weg, das Projekt von Grund auf neu aufzuarbeiten, um tiefgreifende
Erweiterungen einzubauen.
Die Neu-Implementierung des MasterPW-Projekts ermöglicht zwar die Umsetzung von
neuen Features, sollte jedoch auch wieder eine besonders sichere Anwendung
ermöglichen. Neue Vorgänge müssen entsprechend ausgiebig getestet werden, um neue
Sicherheitslücken frühzeitig zu beseitigen.
Diese neuen Funktionen umfassen die Möglichkeit Passwörter als CSV-Dateien zu
exportieren und zu importieren, die Integration eines dedizierten Dienstes zur Validierung
der Passwortsicherheit, die Wiederverwendbarkeit des Backends für anspruchsvollere
Benutzeroberflächen, sowie die Unterstützung von mehreren Benutzern mit angemessener
Vertraulichkeit.
Die Kernziele sind demnach:
- Das Produkt soll die Geschäftsziele des Unternehmens unterstützen, wie z.B. die
Erhöhung der Produktivität und die Verbesserung der Sicherheit von Passwörtern.
- Es muss in der Lage sein, Passwörter und deren Schlüssel zu speichern und zu
verwalten, sowie Passwortstärke zu testen und Berichte darüber zur Verfügung zu
stellen.
- Das System sollte benutzerfreundlich und einfach zu bedienen sein, sicher und
zuverlässig sein, sowie die Möglichkeit bieten, von mehreren Benutzern verwendet
zu werden.
- Gestärkt und erhärtet, muss es skalierbar und wiederverwendbar sein, sowie leicht
wartbar und erweiterbar sein.
- Die Erwartungen und Anforderungen der verschiedenen Stakeholder, wie z.B.
Endbenutzer, IT-Abteilung und Geschäftsführung, müssen berücksichtigt werden,
um sicherzustellen, dass das System ihre Anforderungen erfüllt.


## Aufgabenstellung

Die fachliche Aufgabenstellung ist, ein System zur sicheren Speicherung und Verwaltung
von Passwörtern zu entwickeln, wobei es auch die Passwortstärke über eine dedizierte API
testen und Berichte darüber zur Verfügung zu stellen soll. Weiters soll es Passwörter als
CSV-Dateien ex- und importieren. Das Backend muss für anspruchsvollere
Benutzeroberflächen wiederverwendbar sein und für mehrere Benutzer gleichzeitig
erreichbar sein.
Die treibenden Kräfte hinter dem Projekt sind die Erhöhung der Produktivität und die
Verbesserung der Sicherheit von Passwörtern. Dabei soll das System einfach zu bedienen,
sicher und zuverlässig sein.

Artjom Moisejev if21b055 Nicolas Pozdena if21b057
3
Aufgabenstellung
Die fachliche Aufgabenstellung ist, ein System zur sicheren Speicherung und Verwaltung
von Passwörtern zu entwickeln, wobei es auch die Passwortstärke über eine dedizierte API
testen und Berichte darüber zur Verfügung zu stellen soll. Weiters soll es Passwörter als
CSV-Dateien ex- und importieren. Das Backend muss für anspruchsvollere
Benutzeroberflächen wiederverwendbar sein und für mehrere Benutzer gleichzeitig
erreichbar sein.
Die treibenden Kräfte hinter dem Projekt sind die Erhöhung der Produktivität und die
Verbesserung der Sicherheit von Passwörtern. Dabei soll das System einfach zu bedienen,
sicher und zuverlässig sein.


## Qualitätsziele

Folgende Tabelle illustriert die Top 5 Qualitätsziele für die Architektur:

| Prio | Qualitätsziel | Use-Case |
|------|---------------|----------|
|  1   | Sicherheit    | Passwörter sind mit einer starken Verschlüsselung geschützt und
können nur von autorisierten Benutzern abgerufen werden.
|------|---------------|----------|
|  2   | Skalierbarkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und
können nur von autorisierten Benutzern abgerufen werden.
|------|---------------|----------|
|  3   | Wiederverwendbarkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und
können nur von autorisierten Benutzern abgerufen werden.
|------|---------------|----------|
|  4   | Benutzerfreundlichkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und
können nur von autorisierten Benutzern abgerufen werden.
|------|---------------|----------|
|  5   | Zuverlässigkeit | Passwörter sind mit einer starken Verschlüsselung geschützt und
können nur von autorisierten Benutzern abgerufen werden.

