# TABLE: CREATE

## eine neue Tabelle zur Datenbank hinzufügen

```
CREATE TABLE tabellenname (
   spaltenname_1 <DATENTYP> <EINSCHRÄNKUNG>, 
   spaltenname_2 <DATENTYP> <EINSCHRÄNKUNG>, 
   ... <DATENTYP> <EINSCHRÄNKUNG>, 
   spaltenname_n <DATENTYP> <EINSCHRÄNKUNG>,
   <WEITERE EINSCHRÄNKUNG>,
   ...
)
```
Erstellt eine neue Tabelle mit den angegebenen Spalten. Jede Spalte benötigt einen Datentyp, der angibt, welche Daten in dieser Spalte eingetragen werden können. Neben dem Datentyp können noch  Einschränkungen hinzugefügt werden. Jede Tabelle muss eine Spalte "id" mit dem Datentyp INTEGER und der Einschränkung PRIMARY KEY haben, damit jeder Zeile eine eindeutige Identifikationsnummer zugewiesen werden kann, die automatisch hochgezählt wird.

#### <span><DATENTYP></span>

| Datentyp | Erklärung|
| -------- | -------- | 
| INTEGER  | Ganzzahl     |
| REAL     | Gleitkommazahl     | 
| TEXT     | Text     | 
| BLOB     | Hält Daten genau so, wie diese eingegeben wurden. Ideal z.B. für Dateien oder Bilder.     |

In SQLite gibt es keinen Datentyp für Datumswerte. Diese speichern wir als Text nach ISO8601. Der Syntax hierzu ist YYYY-MM-DD, z.B. 2009-11-13.

#### <span><EINSCHRÄNKUNG></span>

| Einschränkung | Erklärung|
| -------- | -------- | 
| UNIQUE  | Jeder Wert dieser Spalte darf nur einmal vorkommen.     |
| PRIMARY KEY     | Definiert die Werte einer Spalte als Primärschlüssel, anhand derer jede Zeile eindeutig identifizierbar wird. Sie sind automatisch UNIQUE.     | 
| FOREIGN KEY     | Definiert die Werte einer Spalte als Fremdschlüssel.     | 
| NOT NULL     | Legt fest, dass die Werte einer Spalte nicht leer sein dürfen.     |
| DEFAULT <span><wert></span>| Legt einen Standartwert für die Spalte fest, wenn kein Wert eingetragen wird. |



### Beispiel 1:

#### Befehl
```
CREATE TABLE "lehrer" (
    "id" INTEGER PRIMARY KEY, 
    "vorname" TEXT, 
    "nachname" TEXT
)
```
Mit diesem Befehl wird eine Tabelle mit dem Namen lehrer angelegt, die zwei Spalten als TEXT sowie eine Spalte id mit dem Datentyp INTEGER und der Einschränkung PRIMARY KEY hat.


#### Ergebnis:
**Tabelle: lehrer**

|id| vorname   | nachname | 
|--|--------   | -------- | 
| |       |     |

Die neu erstellte Tabelle hat noch keine Einträge, diese können mit dem INSERT INTO-Befehl eingefügt werden.

### Beispiel 2:

#### Befehl
```
CREATE TABLE "klassen" (
    "id" INTEGER PRIMARY KEY, 
    "name" TEXT, 
    "jahrgangsstufe" INTEGER, 
    "lehrer_id" INTEGER,
    FOREIGN KEY "lehrer_id" REFERENCES "lehrer"("id")
)
```
Mit diesem Befehl wird eine Tabelle mit dem Namen klassen angelegt, die mehrere Spalten als TEXT und als INTEGER hat sowie eine Spalte id, mit der Einschränkung PRIMARY KEY. Am Ende des Befehls wird eine Referenz auf eine zweite Tabelle klassen, auf die Spalte id gesetzt.

Dieser Verweis verbindet eindeutig Einträge, die über mehrere Tabellen hinweg verteilt sind. Beispiel: eine Klasse ist genau einem bestimmten Lehrer zugeordnet.


#### Ergebnis:

**Tabelle 2: klassen**

|id| name   | jahrgangsstufe | lehrer_id |
|--|--------   | :-: | :-: |
| |      |     | |
