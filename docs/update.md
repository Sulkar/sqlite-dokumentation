# UPDATE
## einen Wert für alle Datensätze ändern

```
UPDATE tabellenname SET spaltenname = <neuerWert>
oder
UPDATE tabellenname SET spaltenname = <neuerWert> WHERE spaltenname <Operator> <Wert>
```
Mit dem UPDATE Befehl können alle oder einzelne Einträge in einer Tabelle verändert werden.

### Beispiel:

**Tabelle 1: schueler**

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|
|1 | Paul      | Weber    | 2009-07-12   |     1     |25|
|2 | Margot    | Müller   | 2008-11-19   |     2     |5|
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |6|
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |0|
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |3|

#### Befehl

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
UPDATE schueler SET fehltage = 0
```
Mit diesem Befehl werden die Fehltage aller Schüler auf 0 zurückgesetzt. Dies könnte am Ende eines Schuljahres sinnvoll sein.

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|
|1 | Paul      | Weber    | 2009-07-12   |     1     |0|
|2 | Margot    | Müller   | 2008-11-19   |     2     |0|
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |0|
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |0|
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |0|



---


## einen Wert für bestimmte Datensätze ändern

```
UPDATE tabellenname SET spaltenname = <neuerWert> WHERE spaltenname <Operator> <Wert>
```
Mit dem UPDATE Befehl können gezielt Einträge in der Datenbank verändert werden. Die zu ändernden Einträge können mit Hilfe von WHERE und einer passenden Bedingung gewählt werden.

### Beispiel:

**Tabelle 1: schueler**

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|
|1 | Paul      | Weber    | 2009-07-12   |     1     |25|
|2 | Margot    | Müller   | 2008-11-19   |     2     |5|
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |6|
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |0|
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |3|

#### Befehl

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
UPDATE schueler SET klasse_id = 3 WHERE klasse_id = 2
```

Mit diesem Befehl werden alle Schüler*innen die, die klasse_id = 2 haben (Zweitklässler) in die 3. Klasse versetzt (klasse_id = 3).

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|
|1 | Paul      | Weber    | 2009-07-12   |     1     |25|
|2 | Margot    | Müller   | 2008-11-19   |     3     |5|
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |6|
|4 | Sabrina   |  Otto    | 2007-05-19   |     3     |0|
|5 | Ayse      | Ünül     | 2008-12-12   |     3     |3|
