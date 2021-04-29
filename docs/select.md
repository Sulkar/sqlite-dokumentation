# SELECT

<center><img src="/images/Select.png" width="200px"></center>

## Einzelne Spalte ausgeben

```sql
SELECT spaltenname FROM tabellenname
```

Mit diesem Befehl werden alle Zeilen der Spalte "spaltenname" aus der Tabelle "tabellenname" ausgegeben.

### Beispiel

#### Befehl:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
SELECT vorname FROM schueler
```

#### Ergebnis:

| vorname   | 
| --------  | 
| Paul      |
| Margot    |
| Mahmud    |
| Sabrina   |
| Ayse      |



---

## Gezielt mehrere Spalten ausgeben

```
SELECT spaltenname_1, spaltenname_2,...,spaltenname_n FROM tabellenname
```
Hiermit können mehrere Spalten einer Tabelle angezeigt werden. Es werden immer alle Zeilen der selektierten Spalten angezeigt.

### Beispiel

#### Befehl:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
SELECT id, vorname FROM schueler
```

#### Ergebnis:

|id| vorname  | 
| --|-------- | 
|1| Paul     |
|2| Margot   |
|3| Mahmud    |
|4| Sabrina   |
|5| Ayse      |



---


## Alle Spalten ausgeben

```
SELECT * FROM tabellenname
```
Mit diesem Befehl werden alle Zeilen aller Spalten der Tabelle angezeigt.

### Beispiel

#### Befehl:

<a class="runSqlVerine" href="https://sulkar.github.io/SQLverine/" target="_blank"><i class="fa fa-2x fa-arrow-right" ></i></a>
```
SELECT * FROM schueler
```

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | 
|--|--------   | -------- | ------------ | :-------: |
|1 | Paul      | Weber    | 2009-07-12   |     1     |
|2 | Margot    | Müller   | 2008-11-19   |     2     |
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |
