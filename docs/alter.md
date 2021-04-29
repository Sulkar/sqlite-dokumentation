# TABLE: ALTER

<center><img src="/images/neueSpalte.png" width="200px"></center>

## Spalte einer Tabelle hinzufügen

```
ALTER TABLE tabellenname ADD spaltenname <DATENTYP>
```
Dieser Befehl fügt einer Tabelle eine neue Spalte hinzu.

### Beispiel:

**Tabelle: schueler**

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|

#### Befehl:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
ALTER TABLE schueler ADD geburtsort TEXT
```

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage | geburtsort|
|--|--------   | -------- | ------------ | :-------: |:-:|  ---  |



---

## Spalte einer Tabelle löschen

```
ALTER TABLE tabellenname DROP COLUMN spaltenname <DATENTYP>
```
Dieser Befehl löscht eine Spalte einer Tabelle.

### Beispiel:

**Tabelle: schueler**

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage | geburtsort|
|--|--------   | -------- | ------------ | :-------: |:-:|  ---  |


#### Befehl:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
ALTER TABLE schueler DROP COLUMN geburtsort 
```

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|

## Spalte/Tabelle umbennen

```
ALTER TABLE tabellenname RENAME TO tabellenname_neu
```
Dieser Befehl benennt eine Tabelle um.

```
ALTER TABLE tabellenname RENAME spaltenname TO spaltenname_neu
```
Dieser Befehl benennt eine Spalte in der Tabelle um.

### Beispiel 1:

**Tabelle: schueler**

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage | geburtsort|
|--|--------   | -------- | ------------ | :-------: |:-:|  ---  |

#### Befehl:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
ALTER TABLE schueler RENAME fehltage TO absenzen
```
Dieser Befehl benennt die Spalte fehltage der Tabelle schueler in absenzen um.
#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | absenzen | geburtsort|
|--|--------   | -------- | ------------ | :-------: |:-:|  ---  |


### Beispiel 2:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
ALTER TABLE lehrer RENAME TO lehrkraefte
```
Dieser Befehl benennt die Tabelle lehrer in lehrkraefte um.