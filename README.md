# SWARC_arc42
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


## Qualitätsziele

Folgende Tabelle illustriert die Top 5 Qualitätsziele für die Architektur:

| Prio | Qualitätsziel | Use-Case |
|------|---------------|----------|
|  1   | Sicherheit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  2   | Skalierbarkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  3   | Wiederverwendbarkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  4   | Benutzerfreundlichkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  5   | Zuverlässigkeit | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.


## Stakeholder

```
1 = Kennt die Architektur
2 = Muss überzeugt werden
3 = Arbeitet mit Architektur/Code
4 = Benötigt Dokumentation
5 = Trifft Entscheidungen
```

| Stakeholder | Kontakt | 1 | 2 | 3 | 4 | 5 |
|-------------|---------|---|---|---|---|---|
| Projektmanager | projectmanager@example.com | X | - | - | X | X | 
| Architekt | architect@example.com | X  | - | X | X | X 
| Entwickler | developer@example.com | X  | - | X | X | - |
| Tester | tester@example.com | -  | -  | - | X | - |
| IT-Abteilung | it@example.com | X | X | X | X | X |
| Geschäftsführung | ceo@example.com | - | X  | - | X | X |
| Endbenutzer | endbenutzer@example.com | - | X  | - | X | - |
| Password Cops | password-cop@example.com | -  | -  | -  | -  | - |


## Randbedingungen

| Randbedingung | Erläuterung | Kategorie |
|------|---------------|----------|
| Kompatibilität mit bestehenden Systemen | Das neue System muss in die bestehende IT-Infrastruktur des Unternehmens integriert werden und die Anforderungen der bestehenden Systeme erfüllen. | Technisch |
| Budgetbeschränkungen | Das Projekt muss innerhalb eines festgelegten Budgets durchgeführt werden, was Einschränkungen bezüglich der verwendeten Technologien und des Umfangs des Projekts mit sich bringt. | Organisatorisch |
| Datenschutz- und Sicherheitsvorgaben | Die Application muss den geltenden Datenschutz- und Sicherheitsvorschriften entsprechen und die Vertraulichkeit und Integrität der gespeicherten Daten sicherstellen. | Technisch |
| Vorgaben bezüglich Benutzeroberfläche | Das Produkt muss eine benutzerfreundliche Oberfläche aufweisen und dessen Design bestimmte CI/CD Richtlinien einhalten. (Corporate Indentity/Corporate Design) | Technisch |
| Anforderungen an die Skalierbarkeit | Das System muss in der Lage sein, an zukünftige Anforderungen anzupassen und skaliert werden zu können. | Technisch |
| Integrationserfordernisse | Das Backend muss in der Lage sein, mit anderen Systemen und Tools des Unternehmens zu integrieren und Daten auszutauschen | Technisch |
| Compliance-Anforderungen | Das Produkt muss bestimmten Regulierungen und Standards entsprechen, wie z.B. PCI-DSS in Bezug auf Sicherheit der Zahlungsinformationen | Technisch |
| Vorgaben bezüglich des Einsatzes von Third-Party-Tools und Bibliotheken | Das Projekt muss bestimmte Anforderungen an die Verwendung von Third-Party-Tools und Bibliotheken erfüllen. z.B. Lizenzbedingungen und Support-Anforderungen. | Technisch |


## Kontextabgrenzung

### Kommunikation mit dem Backend-Server:
Motivation: Um User Login, User Passwörter und andere Daten speichern und abzurufen.
Fachlichen Komponente: API
Technischen Komponente: HTTP-Protokoll

### Kommunikation mit der PasswordCop API:
Motivation: Nutzung einer dedizierte API (PasswordCop API), die von einem externen
Unternehmen (Password Cops) entwickelt wurde, um die Sicherheit von Passwörtern zu
validieren.
Fachlichen Komponente: API
Technischen Komponente: HTTPS-Protokoll.

### CSV-Import/Export-Funktion:
Motivation: User Passwörter als CSV-Dateien importieren und exportieren.
Fachlichen Komponente: Benutzeroberfläche
Technischen Komponente Dateisystem

### Kommunikation mit Benutzern:
Motivation: Benutzerfreundliche Oberfläche.
Fachlichen Komponente: Benutzeroberfläche
Technischen Komponente (Web-Oberfläche).

### Kommunikation mit der IT-Abteilung:
Motivation: Das System muss mit der IT-Abteilung des Unternehmens zusammenarbeiten,
um in die bestehende IT-Infrastruktur integriert zu werden und betrieben zu werden.
Fachlichen Komponente: Dokumentation der Architektur
Technischen Komponente: Systeminstallation, -konfiguration und -betrieb


## Fachlicher Kontext

| Kommunikationsbeziehung | Eingabe | Ausgabe |
|-------|-------|-------|
| Backend-Server  | Passwort-Informationen im JSON-Format | Bestätigung des erfolgreichen Speicherns oder Abrufens von Passwort-Informationen im JSON- Format |
| PasswordCop API | Passwort im Klartext | Validierungsbericht zur Passwortstärke im JSON-Format |
| CSV-Import/Export | CSV-Datei mit Passwort-Informationen | Bestätigung des erfolgreichen Imports oder Exports von Passwort-Informationen |
| Benutzer | Anforderungen an das Passwort-Management (z.B. Passwort erstellen, importieren, exportieren) über die Benutzeroberfläche | Angezeigte Passwort- Informationen und Validierungsberichte in der Benutzeroberfläche |
| IT-Abteilung | Dokumentation der System-Architektur und Anforderungen an die Integration in die bestehende IT-Infrastruktur | Bestätigung der erfolgreichen Integration und Bereitstellung des Systems |







| title | title | title |
|-------|-------|-------|
| text | text | text |







Score: 100/100
