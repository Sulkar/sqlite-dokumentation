# JOIN

<center><img src="../images/Join.png" width="200px"></center>

## Ergebnisse aus mehreren Tabellen

```
SELECT tabellenname_1.spaltenname_1, tabellenname_2.spaltenname_1 FROM tabellename_1
JOIN tabellenname_2 ON tabellenname_2.id = tabellenname_1.tabellenname_2_id
```
oder
```
SELECT tabellenname_1.*, tabellenname_2.* FROM tabellename_1
JOIN tabellenname_2 ON tabellenname_2.id = tabellenname_1.tabellenname_2_id
```

Mit diesem Befehl werden Informationen aus mehreren Tabellen gleichzeitig abgefragt. Das Ergebnis wird über die jeweiligen IDs verknüpft.

### Beispiel 1:
**Tabelle 1: schueler**

| id | vorname   | nachname | geburtsdatum | klasse_id | 
|----|--------   | -------- | ------------ | :--------: |
|1 | Paul      | Weber    | 2009-07-12   |     1     |
|2 | Margot    | Müller   | 2008-11-19   |     2     |
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |

**Tabelle 2: klassen**

|id| name   | jahrgangsstufe | lehrer_id |
|-----|--------   | :--------: | :--------: |
|1 | 1 A      | 1    | 4|
|2 | 2 A    | 2   |  3|
|3 | 3 A    | 3 |  5|
|4 | 4 A GtK   |  4    |  7|
|5 | 4B      | 4     |  2|



#### Befehl

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
SELECT schueler.vorname, schueler.nachname, klassen.name FROM schueler
JOIN klassen ON klasse.id = schueler.klassen_id
```
Mit diesem Befehl wird abgefragt, welcher Schüler*in in welcher Klasse ist.

#### Ergebnis:

|schueler.vorname|schueler.nachname|<span>klassen.name</span>|
|-|-|-|
| Paul      | Weber    | 1 A   | 
| Margot    | Müller   | 2 A   | 
| Mahmud    | Al'hissi | 1 A   |
| Sabrina   | Otto     | 2 A   |
| Ayse      | Ünül     | 2 A   | 


### Beispiel 2:


**Tabelle 1: schueler**

|id| vorname   | nachname | geburtsdatum | klasse_id | 
|----|--------   | -------- | ------------ | :--------: |
|1 | Paul      | Weber    | 2009-07-12   |     1     |
|2 | Margot    | Müller   | 2008-11-19   |     2     |
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |

**Tabelle 2: klassen**

|id| name   | jahrgangsstufe | lehrer_id |
| -------- | --------   | :--------: | :--------: |
|1 | 1 A      | 1    | 4|
|2 | 2 A    | 2   |  3|
|3 | 3 A    | 3 |  5|
|4 | 4 A GtK   |  4    |  7|
|5 | 4B      | 4     |  2|

**Tabelle 3: lehrer**

|id| vorname   | nachname | 
| -------- | --------   | -------- | 
|2 | Peter      | Müller    |
|3 | Wolfgang    | Schmidt   | 
|4 | Michael   | Schneider | 
|5 | Maria   |  Fischer    |
|7 | Werner   | Geuder     | 

#### Befehl

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
SELECT schueler.vorname, schueler.nachname, lehrer.vorname, lehrer.nachname FROM schueler
JOIN klassen ON klasse.id = schueler.klassen_id
JOIN lehrer ON lehrer.id = klassen.lehrer_id
```
Mit diesem Befehl wird abgefragt, welcher Schüler*in welche Klassenlehrkraft hat. Die drei Tabellen (schueler, klassen, lehrer) werden mittels JOIN miteinander verbunden. Ausgegeben werden aber nur die Spalten (aus Tabelle schueler und Tabelle lehrer), die im SELECT-Befehl eingetragen wurden.

#### Ergebnis:

| schueler.vorname   | schueler.nachname | lehrer.vorname | lehrer.nachname | 
--------   | -------- | -------- | :-: |
| Paul      | Weber    | Michael   | Schneider | 
| Margot    | Müller   | Wolfgang  | Schmidt |
| Mahmud    | Al'hissi | Michael   | Schneider |
| Sabrina   | Otto     | Wolfgang  | Schmidt |
| Ayse      | Ünül     | Wolfgang  | Schmidt |
