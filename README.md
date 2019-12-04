# fir-2019
Datenmodellierung und -analyse mit SQL und Python

# Vorgehensweise und Problemstellung

In diesem Workshop soll beispielhaft der Datenanalyseprozess an Datensätzen der US-Regierung dargestellt werden.

Die Datensätze, mit denen gearbeitet werden soll, sind einmal die der US-Forstbehörde, die eine SQLite3-Datenbank mit Waldbränden veröffentlich hat, sowie die die Niederschlagsdaten der NOAA (National Oceanic and Atmospheric Administration).

Durch die Zusammenführung der Datensätze soll untersucht werden, inwiefern ein Zusammenhang zwischen Trockenheit, Häufigkeit und Größe von Waldbränden besteht.

Die Hypothese ist, dass unterhalb einer bestimmten Niederschlagsmenge in einem bestimmten Zeitraum vor dem Auftreten eines Waldbrands die Wahrscheinlichkeit für das Auftreten dieses Waldbrands über 80% ist.

Hierbei sind Niederschlagsmenge und Untersuchungszeitraum noch unbekannt.

Um diese Untersuchungen praktisch durchführen zu können, benötigt man einige Tools auf dem Rechner. Mit SQL allein wird man die Datenanalyse nicht durchführen können, allerdings ist SQL ein sehr nützliches Tool, um sich die Datensätze zu erzeugen, die man für eine Datenanalyse benötigt.

# Vorbereitungen

## Windows

Für die Analysen werden auf Ihrem Rechner Python und SQLite3 benötigt. Python ist eine Skriptsprache, die für Datenanalysen seit längerer Zeit sehr beliebt ist. SQLite3 ist eine kleine relationale Datenbank, die ganz lokal läuft und keinen Server oder ähnliches benötigt.

### Datenverzeichnis anlegen

Legen Sie zunächst auf Ihrem Rechner ein Verzeichnis an, z.B.
```
C:\datenanalyse
```

Dorthin laden Sie alle Dateien hinunter.


### Python

Unter Windows ist es empfehlenswert, die Python-Distribution Conda zu installieren.

Sie finden Sie hier:

https://docs.conda.io/projects/conda/en/latest/user-guide/install/windows.html

Auf derselben Seite finden sich neben einem Download-Link auch Installationsanleitungen.


### Download SQLite3

SQLite3 finden Sie unter folgendem Link:

https://sqlite.org/2019/sqlite-tools-win32-x86-3300100.zip

Speichern Sie diese Datei in dem Projektverzeichnis, z.B. ``C:\datenanalyse``.

Dort enpacken Sie die Datei auch.

### Waldbrand-Daten

Die Daten für die Waldbrände finden Sie unter folgender Adresse:

https://www.fs.usda.gov/rds/archive/products/RDS-2013-0009.4/RDS-2013-0009.4_SQLITE.zip

Speichern Sie diese Datei in dem Projektverzeichnis, z.B. ``C:\datenanalyse``.


Meta-Informationen über diesen Datensatz finden Sie hier:

https://www.fs.usda.gov/rds/archive/catalog/RDS-2013-0009.4


### Niederschlagsdaten

Die Niederschlagsdaten sollen im Zeitraum 2011 bis 2014 betrachtet werden.

Sie finden sie entweder unter

https://www1.ncdc.noaa.gov/pub/data/15min_precip-3260/

Hier interessieren die Datensätze:
by_month2011.zip
by_month2012.zip
by_month2013.zip
by_month2014.zip

oder auch in diesem Repo unter niederschlag/data.

Speichern Sie diese Datei in dem Projektverzeichnis, z.B. ``C:\datenanalyse``.


# Daten verstehen

Um die Daten analysieren zu können, muss man diese zuerst verstehen und dann aufbereiten.

Dies ist ein Thema, das eher dem Data Engineering zugeordnet werden könnte, aber Data Engineering und Data Science lassen sich voneinander nicht trennen. Insbesondere ist ein sauberes Data Engineering Vorbedingung für jede erfolgreiche Datenanalyse.

Eine der Hauptaussagen dieses Workshops ist es, eindringlich zu vermitteln, dass man ohne sauberes Data Engineering keine Data Science-Projekte durchführen kann.

## Niederschlagsdaten

Unter dem Ordner "niederschlag" finden Sie Informationen zu den Niederschlagsdaten des NOAA.

In diesem Repo finden Sie neben ein paar Beispieldaten auch ein PDF, in dem das Datenformat dokumentiert ist.

Es handelt sich um das Dokument "dsi3260.pdf". Die Datei "ca_2011-01.txt" liefert ein paar Beispieldaten.

### Aufgabe: Betrachten Sie die Beispieldaten und die Dokumentation. Versuchen Sie zu verstehen, wie die Datensätze aufgebaut sind. Identifizieren Sie die Entities, die in den Datensätzen dokumentiert werden. Entwickeln Sie ein relationales Datenmodell für diese Rohdaten.

Das Beispiel ist durchaus realistisch. In vielen Systemen kommen kryptische Datenformate vor, die man nicht direkt auswerten kann. Diese muss man zunächst verstehen und in eine auswertbare Form überführen.

#### Take-Away: Das Engineering von Daten kann zeitintensiv und aufwendig sein. Dem Kunden ist es manchmal schwer zu vermitteln, dass relativ viele Ressourcen in das Engineering der Daten fließen müssen, bevor überhaupt eine einzige Auswertung gemacht werden konnte. Dennoch ist der Automatisierungsgrad bei der Bereitstellung auszuwertender Datensätze manchmal noch gering und erfordert nicht zu vernachlässigende Aufwände durch Spezialisten.





# Datenbank für Niederschlag einrichten

```
CREATE TABLE niederschlag (id integer primary key autoincrement, 
                           year integer, 
                           month integer, 
                           day integer, 
                           state_code integer, 
                           state text(3), 
                           station_id text, 
                           zeitslot integer, 
                           menge integer);

```
