# INSERT

## eine neue Zeile einer Tabelle hinzufügen

```
INSERT INTO tabellenname (spaltenname_1, spaltenname_2, ..., spaltenname_n) 
VALUES (<wert_1>, <wert_2>, ..., <wert_n>)
```
Mit dem INSERT INTO Befehl wird eine neue Zeile einer Tabelle hinzugefügt. Neben dem Tabellennamen müssen alle zu befüllenden Spaltennamen der Tabelle in Klammern dahinter eingetragen werden. Nur die Spalte "id", die automatisch hochgezählt wird und einzigartig sein muss, wird nicht mit aufgeführt. Bei VALUES müssen die Werte in der richtigen Reihenfolge, passend der Reihenfolge der Spaltennamen, eingetragen werden.


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
```
INSERT INTO tabellenname (vorname, nachname, geburtsdatum, klasse_id, fehltage) 
VALUES ('Ullrich', 'Gcheuder', '2006-07-05', 3, 20)
```
Mit diesem Befehl wird ein weiterer Schüler angelegt.

#### Ergebnis:

|id| vorname   | nachname | geburtsdatum | klasse_id | fehltage |
|--|--------   | -------- | ------------ | :-------: |:-:|
|1 | Paul      | Weber    | 2009-07-12   |     1     |25|
|2 | Margot    | Müller   | 2008-11-19   |     2     |5|
|3 | Mahmud    | Al'hissi | 2008-06-30   |     1     |6|
|4 | Sabrina   |  Otto    | 2007-05-19   |     2     |0|
|5 | Ayse      | Ünül     | 2008-12-12   |     2     |3|
|6 | Ullrich   | Gcheuder     | 2006-07-05   |     3     |20|


