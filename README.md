
# Sudoku Solver

Ein Sudoku-Solver in Java, der mithilfe eines rekursiven Backtracking-Algorithmus 9x9-Sudokus löst.

Das Projekt wurde im Rahmen einer Hausübung im Studium Software Engineering und vernetzte Systeme entwickelt.

## Regeln

Ein gültiges 9x9-Sudoku muss folgende Bedingungen erfüllen:

- Jede Zahl von 1 bis 9 darf in einer Zeile nur einmal vorkommen.
- Jede Zahl von 1 bis 9 darf in einer Spalte nur einmal vorkommen.
- Jede Zahl von 1 bis 9 darf in einem 3x3-Block nur einmal vorkommen.
- `0` steht für ein leeres Feld.

## Eingabe

Das Sudoku kann über ein Menü eingegeben oder aus der Datei `input.csv` eingelesen werden.

Die CSV-Datei enthält neun Zeilen mit jeweils neun durch Kommas getrennten Zahlen.

Beispiel (erste drei Zeilen):

```text
5,3,0,0,7,0,0,0,0
6,0,0,1,9,5,0,0,0
0,9,8,0,0,0,0,6,0
```

## Funktion

Das Programm:

1. liest ein Sudoku ein,
2. überprüft, ob Zahlen an einer bestimmten Position gültig sind,
3. löst das Sudoku mithilfe von rekursivem Backtracking,
4. gibt das gelöste Sudoku aus oder meldet, wenn keine Lösung existiert.

Der Einstiegspunkt des Solvers ist:

```java
public static int[][] solve(int[][] sudoku)
```

## Installation und Ausführung

### Voraussetzungen
- Java JDK 17 oder neuer
- Maven
- IntelliJ IDEA oder eine andere Java-IDE


### Programm starten

1. Repository herunterladen oder klonen.
2. Das Projekt in IntelliJ IDEA öffnen.
3. Maven-Abhängigkeiten laden lassen.
4. Die Klasse `Main.java` ausführen.

Beim Start wird über `SudokuMenu.run()` das Menü geöffnet.

Dort kann ein Sudoku eingegeben oder aus einer CSV-Datei eingelesen und anschließend gelöst werden.


## Technologien

- Java
- Maven
- JUnit

## Dokumentation

Weitere Informationen zur Datenstruktur, zum Backtracking-Algorithmus sowie zur Zeit- und Platzkomplexität befinden sich in der [Dokumentation](Dokumentation.md).
