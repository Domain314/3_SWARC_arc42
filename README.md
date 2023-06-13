# SWARC_arc42
Software Architecture - arc42 filled out (German)

### MasterPW NG

## Über arc42

_arc42_, das Template zur Dokumentation von Software- und Systemarchitekturen.
Erstellt von Dr. Gernot Starke, Dr. Peter Hruschka und Mitwirkenden.
Template Revision: 7.0 DE (asciidoc-based), January 2017
© We acknowledge that this document uses material from the _arc42_ architecture template,
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


### Aufgabenstellung

Die fachliche Aufgabenstellung ist, ein System zur sicheren Speicherung und Verwaltung
von Passwörtern zu entwickeln, wobei es auch die Passwortstärke über eine dedizierte API
testen und Berichte darüber zur Verfügung zu stellen soll. Weiters soll es Passwörter als
CSV-Dateien ex- und importieren. Das Backend muss für anspruchsvollere
Benutzeroberflächen wiederverwendbar sein und für mehrere Benutzer gleichzeitig
erreichbar sein.
Die treibenden Kräfte hinter dem Projekt sind die Erhöhung der Produktivität und die
Verbesserung der Sicherheit von Passwörtern. Dabei soll das System einfach zu bedienen,
sicher und zuverlässig sein.


### Qualitätsziele

Folgende Tabelle illustriert die Top 5 Qualitätsziele für die Architektur:

| Prio | Qualitätsziel | Use-Case |
|------|---------------|----------|
|  1   | Sicherheit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  2   | Skalierbarkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  3   | Wiederverwendbarkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  4   | Benutzerfreundlichkeit    | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.
|  5   | Zuverlässigkeit | Passwörter sind mit einer starken Verschlüsselung geschützt und können nur von autorisierten Benutzern abgerufen werden.


### Stakeholder

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

**Kommunikation mit dem Backend-Server:**
Motivation: Um User Login, User Passwörter und andere Daten speichern und abzurufen.
Fachlichen Komponente: API
Technischen Komponente: HTTP-Protokoll

**Kommunikation mit der PasswordCop API:**
Motivation: Nutzung einer dedizierte API (PasswordCop API), die von einem externen
Unternehmen (Password Cops) entwickelt wurde, um die Sicherheit von Passwörtern zu
validieren.
Fachlichen Komponente: API
Technischen Komponente: HTTPS-Protokoll.

**CSV-Import/Export-Funktion:**
Motivation: User Passwörter als CSV-Dateien importieren und exportieren.
Fachlichen Komponente: Benutzeroberfläche
Technischen Komponente Dateisystem

**Kommunikation mit Benutzern:**
Motivation: Benutzerfreundliche Oberfläche.
Fachlichen Komponente: Benutzeroberfläche
Technischen Komponente (Web-Oberfläche).

**Kommunikation mit der IT-Abteilung:**
Motivation: Das System muss mit der IT-Abteilung des Unternehmens zusammenarbeiten,
um in die bestehende IT-Infrastruktur integriert zu werden und betrieben zu werden.
Fachlichen Komponente: Dokumentation der Architektur
Technischen Komponente: Systeminstallation, -konfiguration und -betrieb


### Fachlicher Kontext

| Kommunikationsbeziehung | Eingabe | Ausgabe |
|-------|-------|-------|
| Backend-Server  | Passwort-Informationen im JSON-Format | Bestätigung des erfolgreichen Speicherns oder Abrufens von Passwort-Informationen im JSON- Format |
| PasswordCop API | Passwort im Klartext | Validierungsbericht zur Passwortstärke im JSON-Format |
| CSV-Import/Export | CSV-Datei mit Passwort-Informationen | Bestätigung des erfolgreichen Imports oder Exports von Passwort-Informationen |
| Benutzer | Anforderungen an das Passwort-Management (z.B. Passwort erstellen, importieren, exportieren) über die Benutzeroberfläche | Angezeigte Passwort- Informationen und Validierungsberichte in der Benutzeroberfläche |
| IT-Abteilung | Dokumentation der System-Architektur und Anforderungen an die Integration in die bestehende IT-Infrastruktur | Bestätigung der erfolgreichen Integration und Bereitstellung des Systems |


### Technischer Kontext

| Kommunikationskanal | Eingabe | Ausgabe |
|-------|-------|-------|
| HTTPS-Verbindung zum Backend-Server | Passwort-Informationen im JSON-Format | Bestätigung des erfolgreichen Speicherns oder Abrufens von Passwort-Informationen im JSON-Format |
| HTTPS-Verbindung zur PasswordCop API | Passwort im Klartext | Validierungsbericht zur Passwortstärke im JSON-Format |
| Dateisystem für CSV-Import/Export | CSV-Datei mit Passwort-Informationen | Bestätigung des erfolgreichen Imports oder Exports von Passwort-Informationen |
| Web-basierte Benutzeroberfläche | Anforderungen an das Passwort-Management (z.B. Passwort erstellen, importieren, exportieren) | Angezeigte Passwort-Informationen und Validierungsberichte |
| SSH/RDP Verbindung zu IT Abteilung | Dokumentation der System-Architektur und Anforderungen an die Integration | Bestätigung der erfolgreichen Integration und Bereitstellung des Systems |


## Lösungsstrategie

Die zentralen Entwurfsentscheidungen des Systems beinhalten:
- Die Verwendung einer modernen Programmiersprache und Technologie-Stack für Server- und Client-Seite, um Anforderungen an Performance, Skalierbarkeit und Sicherheit zu erfüllen
- Eine saubere Trennung der Schichten (Präsentationsschicht, Geschäftslogik und Datenschicht) um Flexibilität und Wiederverwendbarkeit zu erhöhen
- Eine integrierte Passwortstärken-Prüfung durch die Verwendung einer dedizierten API, um die Sicherheit von Passwörtern zu gewährleisten
- Eine Benutzeroberflächen-Design unter Berücksichtigung der Usability-Standards
- Agile Entwicklungsmethoden um einen reibungslosen Ablauf des Projekts zu gewährleisten und Aufgaben und Verantwortungen klar zu delegieren


## Bausteinsicht

### Whitebox Gesamtsystem
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/8769a64a-2ab2-44ac-9b64-c3c3c71c145a)

**Begründung:**
Die Aufteilung der Verantwortlichkeiten der Bausteine ist geplant so dass einzelne Teile durch andere Funktionalitäten ausgetauscht werden können ohne die anderen Bausteine zu beeinflussen.

**Enthaltene Bausteine:**
In der ersten Ebene des Gesamtsystems sind folgende essentielle Bausteine vorhanden: der ClientHandler, der APIHandler, der BackendServer und der LocalStorage.

**Wichtige Schnittstellen:**
Der PasswordSafe bietet via dem ClientHandler dem User die Schnittstelle für Input und Output.
Weiters wird die externe Schnittstelle der PasswordCopAPI verwendet um Passwortsicherheit zu gewährleisten

### ClientHandler
- Verwaltet den Input und Output mit dem User.
- Bietet dem User eine Schnittstelle um mit dem PasswordSafe zu interagieren und verwendet die vom BackendServer bereitgestellte Schnittstelle

### APIHandler
- Steuert die Kommunikation mit der PasswordCopAPI.
- Stellt dem BackendServer die PasswordCopAPI zur Verfügung.
- Beinhaltet das Exceptionhandling wenn die PasswordCopAPI nicht erreichbar ist.
- Als separate Blackbox vom BackendServer erlaubt es der APIHandler jederzeit die API zur Überprüfung der Passwörter zu ändern ohne den BackendServer zu beeinflussen.

### BackendServer
- Verwaltet die Request des Users welche vom ClientHandler weitergereicht werden (Abfragen, Ändern und Hinzufügen von Passwörtern)
- Kümmert sich um die Authentifizierung der User
- Stellt das Bindeglied zwischen LocalStorage, ClientHandler und APIHandler

### LocalStorage
- Verarbeitet Schreib- und Leseanfragen and die Passwortdatenbank.
- Beinhaltet die Ver- und Entschlüsselung von Passwörter



## Ebene 2

### LocalStorage <Import/ExportHandler>
Der Import/ExportHandler nimmt Passwörter oder Listen an Passwörtern vom BackendServer entgegen und gibt auch einzelne Passwörter oder Listen an Passwörtern zurück.

### LocalStorage <DE/EncryptionHandler>
Nimmt Passwörter oder verschlüsselte Zeichenketten entgegen und gibt verschlüsselte Zeichenketten oder entschlüsselte Passwörter zurück.

### LocalStorage <DatabaseHandler>
Schreibt oder liest gespeicherte Passwortdaten aus.
  
### BackendServer <RequestHandler>
Nimmt die Requests aus dem ClientHandler entgegen und schickt Responses mit den Daten welche aus anderen Bausteinen gesammelt wurden.

### BackendServer <AuthenticationHandler>
Nimmt AuthenticationRequests entgegen und authentifiziert die User gegen eine gewünschte Directory

  
  
  
## Laufzeitsicht
  
### Passwort hinzufügen
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/c52c05d5-403e-4654-b8f1-7cbe633e982e)

**Beschreibung:** Nachdem der User authentifiziert wurde, wird die Passwordstärke mittels dedizierter API von PaswordCop geprüft und ausgegeben. Beim Bestehen des Tests wird das Passwort an den LocalStorage gesendet, verschlüsselt und gespeichert.
  
  
### Passwort abfragen  
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/fad93237-429d-4202-8e61-eb88699a3f9a)

**Beschreibung:** 
Nachdem der User authentifiziert wurde, wird das eingegebene Passwort abgerufen, entschlüsselt und ausgegeben
  
### Passwort ist nicht stark genug
  
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/a86a658c-280f-4c53-9f96-6645ba285d34)
 
**Beschreibung:** 
Wenn die Passwortstärke die Tests von PasswordCop nicht besteht, wird eine Fehlermeldung ausgegeben.  
  
  
 
## Verteilungssicht
  
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/27f4f128-6e60-46f4-9f94-6c3d422c8935)
  
**Begründung:**
Da die Anforderungen sowohl Wiederverwendbarkeit als auch eine REST-Schnittstelle fordern ist die Kommunikation zwischen den einzelnen Bausteinen auf JSON und HTTPS Basis. 
Hierbei können Werte sowohl als einzelne Passwörter als auch als Listen übertragen werden.
  
**Qualitäts- und/oder Leistungsmerkmale**
HTTPS und JSON erlauben nicht nur für eine verschlüsselte und sichere Übertragung sondern bieten zukünftigen Entwicklern auch eine Möglichkeit der Lesbarkeit der einzelnen Kommunikationskomponenten, da JSON auch für einen Menschen verständlich aufgebaut ist
  
 
  
## Querschnittliche Konzepte
  
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/c208a74a-402e-496c-82c6-dd1ce32a7841)

### User Experience
Mit einer Benutzeroberfläche welche Usern den Import und Export von Passwörtern sowie das einfache Abfragen, Hinzufügen und Ändern von Passwörtern erlaubt, kann diese Lösung Berührungsängsten mit dem neuen PasswortSafe vorbeugen.
  
### Sicherheitskonzepte
Wie bereits in vorherigen Teilen des ARC42 Templates erwähnt wurde, ist ein großer Teil der Sicherheit auf Basis von Authentifizierung und Verschlüsselung. Sämtliche Passwortdaten werden verschlüsselt gespeichert und nur authentifizierte User können auf ihre Passwörter zugreifen.
  
### Betriebskonzepte
Da die Lösung auf den eigenen Firmenservern gehostet wird bietet es den Usern eine hohe Verfügbarkeit im Firmennetzwerk an. Die Anzahl an Passwortdaten und Usern kann beliebig gewählt werden und bietet daher eine ausgezeichnete Skalierbarkeit.
  
### Unter-der-Haube
Auftretende Fehler welche sowohl vom User (z.B. Password entspricht nicht den Anforderungen) als auch vom System (z.B. Nicht-Erreichbarkeit von PasswordCop) werden erkannt und als verständliche Fehlermeldung an den User übermittelt.
  
  
## Entwurfsentscheidungen
  
**Datenbankdesign:** Mit einem MongoDB/JSON Backend, welches über eine API kommuniziert, haben wir die Möglichkeit die Datensätze beliebig zu skalieren und mit modernen Datenbanktechnologien zu arbeiten.
  
**Verschlüsselungstechnologie:** Eine starke Verschlüsselungstechnologie (AES-256), ermöglicht die Passwörter langfristig zu schützen und sicherzustellen, dass sie nur von autorisierten Benutzern abgerufen werden können.
  
**Password-Cops API:** Die Passwortstärke wird über eine dedizierte API kalkuliert, somit legen wir die Verantwortung aus, auf dem aktuellsten Stand der Passwort-Stärke zu bleiben und auch die betrieblichen Kosten der Kalkulationen selbst, bleiben uns erspart.
(Siehe Laufzeitsicht)
  
**Wiederverwendbarkeit:** Eine modularisierte Architektur, um das Backend schnell und einfach an andere Frontends anzubinden und um es für die Entwicklung von verschiedenen Clients zu nutzen. 
(Siehe Whitebox)
  
**Local Storage:** Die Passwörter werden auch lokal gespeichert, um den offline Betrieb zu ermöglichen und auch um die eigenen Server zu schonen.
  
**Benutzerfreundlichkeit:** Die Gestaltung einer intuitiven Benutzeroberfläche, um das System einfach zu bedienen.
  
**CSV-Import/Export:** Die Passwörter werden als CSV exportiert, da es der gängige und kompatible Weg ist, um es auch mit anderen Applikationen und Webanwendungen zu benutzen. Alternativ wäre eine proprietäres Datenformat, um die sichere Ablage zu gewährleisten, jedoch wäre dies nicht kompatibel mit anderen Anwendungen
  
**Zuverlässigkeit:** Das System ist verfügbar und fehlerfrei, auch unter Lastbedingungen und hoher Benutzeraktivität.
  
  
## Qualitätsbaum  
  
![image](https://github.com/Domain314/3_SWARC_arc42/assets/65196868/15771294-5e40-490a-9e4e-a78902f58b5e)
 

## Qualitätsszenarien
  
| Titel | Szenario | Output |
|-------|-------|-------|
| Abrufen von Passwörtern | Der Benutzer gibt seine Anmeldeinformationen ein und wählt das gewünschte Passwort aus. | Entschlüsselung des Passworts und Ausgabe an den Benutzer. |
| Erstellung eines neuen Passworts | Der Benutzer möchte ein Passwort speichern | Prüfung der Passwortstärke mithilfe der integrierten API und Ausgabe eines Validierungsberichts. Wenn das Passwort den Anforderungen entspricht, wird es verschlüsselt gespeichert |
| Passwort Importieren | Der Benutzer möchte seine Passwörter vom Backup importieren. | Der Benutzer lädt eine CSV-Datei mit Passwort-Informationen hoch. Das System importiert die Passwörter, prüft ihre Stärke und speichert sie verschlüsselt. |
| Passwort Exportieren | Der Benutzer möchte seine Passwörter als Backup exportieren. | Der Benutzer wählt die Passwörter aus, die er exportieren möchte und das System erstellt eine CSV-Datei mit den ausgewählten Passwort-Informationen. |
| Mehrbenutzerunter stützung | Ein Unternehmen möchte die Passwörter der Mitarbeiter verwalten. | Ein Admin erstellt neue Benutzeraccounts und gibt diesen Zugriffsrechte auf bestimmte Passwörter. Jeder Benutzer kann nur auf die ihm zugewiesenen Passwörter zugreifen und verändern. |
| Passwortänderung | Ein User möchte sein Passwort ändern | Erneute Überprüfung der Passwortstärke. Anschließend verschlüsseln und speichern. |
| Passwort-Ablauf  | Ein User hat sein Passwort zu lange nicht gewechselt | Die Application hat eine Funktionalität eingebaut, um sicherzustellen, dass Passwörter regelmäßig geändert werden. Wenn ein Passwort abläuft, wird der Benutzer benachrichtigt und aufgefordert, ein neues Passwort zu erstellen. |
| Sicherheitsbericht  | Der User möchte einen Bericht zur Sicherheit seiner Passwörter. | Das System generiert einen Bericht, der die Stärke der Passwörter, sowie deren Alter und Letztes Änderungsdatum enthält. |
  
  
## Risiken und technische Schulden
  
| Risiko | Szenario | Lösung |
|-------|-------|-------|
| Performance | Hohe Last  | Optimierung der Datenbankabfragen und Implementierung von Caching-Mechanismen. |
| Sicherheitsrisiko | Angriff auf die Passwortdatenbank | Erhöhung der Passwortverschlüsselung und Implementierung von Sicherheitsmechanismen wie Zwei-Faktor-Authentifizierung |
| Wartbarkeit | Komplizierte Updates zB.: tiefgreifende Sicherheitsupdates | Implementierung von automatisierten Tests, um die Qualität des Codes zu gewährleisten und zukünftige Änderungen zu erleichtern. |
| Usability | Die Benutzeroberfläche des Systems zu kompliziert | Durchführung von Usability-Tests und Implementierung von Verbesserungsvorschlägen aus dem Feedback der Benutzer. |
| Skalierbarkeit | Anzahl der Benutzer oder die Anzahl der gespeicherten Passwörter steigt zu schnell an. | Analysieren des Systems auf skalierbarkeitsschwache Stellen und Implementierung von Skalierungsmaßnahmen wie horizontaler Skalierung oder den Einsatz von Cloud-Technologien |
| Kompatibilität | Ungetestete Umgebung zB: Linux | Überprüfung der Kompatibilität des Systems mit anderen Systemen und Plattformen und gegebenenfalls Anpassungen vornehmen. |
| Verfügbarkeitsrisiko | Zu viele Anfragen gleichzeitig oder wenn es zu Fehlern oder Ausfällen kommt. | Implementierung von Maßnahmen zur Erhöhung der Verfügbarkeit des Systems, wie zum Beispiel die Verwendung von redundanter Hardware oder die Verwendung von Lastverteilungs-Technologien. |
  
  
## Glossar
  
| Begriff | Definition |
|-------|-------|
| Autorisierung | Prozess, bei dem festgestellt wird, ob ein Benutzer das Recht hat, auf eine bestimmte Ressource zuzugreifen. |
| Verschlüsselung | Verfahren zur Umwandlung von Klartext in verschlüsselten Text, um die Datensicherheit zu erhöhen. |
| Passwortstärketest | Überprüfung, ob ein Passwort bestimmte Kriterien erfüllt, die für eine sichere Verwendung empfohlen werden |
| Import/Export  | Übertragung von Daten in oder aus einem System. |
| Datenbank | System zur Speicherung, Verwaltung und Abfrage von Daten. |
| Backend | Teil eines Systems, der sich um die Verarbeitung von Daten kümmert, aber nicht direkt vom Benutzer interagiert |
| Frontend | Teil eines Systems, der die Benutzerinteraktion ermöglicht und die Daten vom Backend anzeigt. |
| Anwendungsserver | Server, auf dem Anwendungen ausgeführt werden. |
| Benutzeroberfläche/UI  | Schnittstelle zwischen Benutzer und System, die es ermöglicht, mit dem System zu interagieren. |
| Datensicherheit | Schutz von Daten vor unbefugtem Zugriff, Veränderung oder Löschung. |
| Skalierbarkeit | Fähigkeit eines Systems, bei steigender Last gleichbleibend effizient zu arbeiten. |
| Zuverlässigkeit | Fähigkeit eines Systems, korrekt und verlässlich zu funktionieren. |
| Benutzerfreundlichkeit  | Einfachheit und Intuitivität der Benutzererfahrung. |
| API-Schnittstelle  | Schnittstelle, die es ermöglicht, auf die Funktionalität eines Backends über das Web zuzugreifen. |
| Netzwerksicherheit  | Schutz von Netzwerken vor Cyberbedrohungen. |
| Passwortmanagement  | Verwaltung von Passwörtern, einschließlich Generierung, Speicherung und Verwaltung. |
| Schlüsselmanagement | Verwaltung von Kryptografischen Schlüsseln, einschließlich Generierung, Speicherung und Verwaltung |
  
  
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

Score: 100/100

Kommentar von Lektor: _"Die Ausarbeitung beinhaltet sämtliche vom Arc42 benötigten Inhalte."_

