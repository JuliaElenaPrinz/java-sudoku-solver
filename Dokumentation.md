# Datenstruktur
Für das Sudoku wurde ein zweidimensionales Array vom Typ `int[][]` gewählt. Die Größe wird beim Erstellen auf 9×9 festgelegt, da das Sudoku aus neun Zeilen und neun Spalten besteht.

Das Array speichert ganze Zahlen von 0 bis 9. Dabei steht 0 für ein leeres Feld.

Diese Datenstruktur eignet sich, weil sie den Aufbau des Sudoku-Rasters direkt abbildet. Über den Zeilen- und Spaltenindex kann auf jedes Feld zugegriffen werden. Die gespeicherten Zahlen können während des Lösens verändert werden, während die Größe des Arrays gleich bleibt.

# Backtracking
Das Sudoku wird von oben links zeilenweise von links nach rechts durchsucht. Beim ersten leeren Feld, das durch 0 gekennzeichnet ist, werden die Zahlen von 1 bis 9 aufsteigend ausprobiert.

Die Methode `isValid()` prüft mithilfe von `isNumberInRow()`, `isNumberInColumn() `und `isNumberInBox()`, ob die Zahl bereits in der Zeile, Spalte oder im 3×3-Block vorkommt. Wenn alle drei Methoden `false` zurückgeben, darf die Zahl eingesetzt werden.

Anschließend ruft sich die Methode `isSudokuSolvable()` rekursiv selbst auf, um das nächste leere Feld zu bearbeiten. Kann dort mit keiner Zahl eine Lösung gefunden werden, wird false zurückgegeben. Der vorherige Aufruf setzt seine eingesetzte Zahl wieder auf 0 und versucht die nächste Zahl.

Sind keine leeren Felder mehr vorhanden, wird `true` zurückgegeben. Wenn alle Möglichkeiten erfolglos ausprobiert wurden, liefert der `Solver` null zurück.

### Warum Backtracking?
Backtracking eignet sich für Sudoku, da für ein leeres Feld mehrere Zahlen infrage kommen können. Der Algorithmus probiert die erlaubten Zahlen systematisch aus. Führt eine Zahl später in eine Sackgasse, wird sie entfernt und die nächste Möglichkeit ausprobiert.


# Zeitkomplexität
Der Sudoku-Solver verwendet einen rekursiven Backtracking-Algorithmus.
Bei jedem leeren Feld werden maximal neun Zahlen ausprobiert. Bei n leeren Feldern ergibt sich theoretisch eine obere Schranke von O(9^n). <br>
Da meine Implementierung ausschließlich Sudokus mit einer festen Größe von 9x9 unterstützt, ist die Anzahl der Felder jedoch auf 81 begrenzt. <br>
Die asymptotische Zeitkomplexität beträgt deshalb O(1).

In der Praxis kann sich die benötigte Rechenzeit dennoch stark unterscheiden, da manche Sudokus
wesentlich mehr Backtracking-Schritte benötigen als andere.

## Best Case
Das Sudoku ist bereits gelöst oder kann ohne Backtracking vervollständigt werden.
## Average Case
Die tatsächliche Anzahl der Versuche hängt von der Anordnung der vorgegebenen Zahlen ab.
Eine genaue durchschnittliche Laufzeit lässt sich ohne weitere Annahmen nicht bestimmen.
## Worst Case
Der Algorithmus muss sehr viele mögliche Zahlenkombinationen ausprobieren.
Da die maximale Anzahl der Felder fest begrenzt ist, bleibt die asymptotische Komplexität auch im Worst Case O(1).

# Platzkomplexität
Das Sudoku wird direkt im vorhandenen zweidimensionalen Array verändert. Es werden keine Kopien des Sudoku-Rasters erstellt.<br>
Da die Größe des Arrays fest auf 9x9 begrenzt ist, benötigt es konstanten Speicherplatz.<br>
Bei jedem rekursiven Aufruf muss sich das Programm merken, an welcher Stelle es danach weitermachen soll. Die maximale Rekursionstiefe ist durch die Anzahl der leeren Felder begrenzt und kann höchstens 81 betragen.<br>
Bei einer theoretisch variablen Anzahl von n leeren Feldern beträgt der zusätzliche Speicherbedarf durch die Rekursion O(n).<br>
Da meine Implementierung jedoch ausschließlich Sudokus mit 9x9 Feldern verarbeitet, ist auch die maximale Rekursionstiefe konstant begrenzt.<br>
Die asymptotische Platzkomplexität beträgt daher O(1).


Benutze Hilfestellungen:
- https://www.intervue.io/top-coding-questions/java/sudoku-solver/
- https://www.geeksforgeeks.org/dsa/sudoku-backtracking-7/
- https://www.baeldung.com/java-sudoku
- https://www.youtube.com/watch?v=mcXc8Mva2bA&t=1081s
- https://www.youtube.com/watch?v=9I73elFoze8
