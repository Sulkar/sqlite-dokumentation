# DELETE

<center><img src="../images/Drop.png" width="200px"></center>

## alle Einträge einer Tabelle löschen
```
DELETE FROM tabellenname
```
Dieser Befehl löscht alle Einträge einer Tabelle.

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
DELETE FROM schueler
```

Mit diesem Befehl werden alle Schüler*innen der Schule gelöscht.

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|

<center><img src="../images/Delete.png" width="200px"></center>

## bestimmte Einträge einer Tabelle löschen
```
DELETE FROM tabellenname WHERE  spaltenname <Operator> <Wert>
```
Dieser Befehl löscht alle Einträge einer Tabelle, die mit Hilfe von WHERE und einer passenden Bedingung gewählt werden. 

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
DELETE FROM schueler WHERE vorname LIKE 'Ma%'
```

Mit diesem Befehl werden alle Schüler*innen der Schule gelöscht, deren Vorname mit "Ma" beginnt.

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|
|1 | Paul      | Weber    | 2009-07-12   |     1     |25|
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |0|
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |3|
