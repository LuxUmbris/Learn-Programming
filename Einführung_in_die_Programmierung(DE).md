# Einstieg in die Programmierung
###### Document version: 1.0.0 (DE)

Dies ist eine grundlegende Einführung in die Programmierung.
1. [Grundlagen des Programmierens](#grundlagen-des-programmierens) \
1.1 [Variablen](#variablen) \
1.2 [Datentypen](#datentypen) \
1.3 [Funktionen](#funktionen) \
1.4 [Kommentare](#kommentare)
2. [Einführung in Python](#python) \
2.1 [Blöcke (Scopes)](#blöcke-scopes) \
2.2 [Variablen in Python](#variablen-in-python) \
2.3 [Funktionen in Python](#funktionen-in-python)
3. [Andere Programmiersprachen](#andere-programmiersprachen)
4. [Einstieg in die Systemprogrammierung]()
5. [Einführung in C++](#einführung-in-c--)
6. [Meine Sprache (C<<)](#meine-sprache)
7. [Installation und Nutzung von Werkzeugen]()

## Grundlagen des Programmierens
### Variablen
Bestimmt kennst du das bereits aus dem Matheunterricht: Eine variable ist in gewisser Weise ein Ersatz für einen Wert. Beispiel:
```Python <!-- Das Python Präfix ist nur für Syntax highlighting, nicht garantiert valider Code (Sieht man im Preview aber auch nicht) -->
x = 5
```
Und jetzt können wir diesen Wert für eine Rechnung nutzen:
```Python
x + 2
```
Die Variable `x` ist `5`, was heißt `x + 2` ist das selbe wie `5 + 2`.
Jetzt fragst du dich sicher:  
Gut, aber wieso nutzen wir dann überhaupt variablen? \
Ganz einfach: stell dir vor, du hast eine Bank. Diese Bank gibt all ihren Klienten 1,5% Zinsen. Das sähe ungefär so aus:
```Python
Gehalt1 * 0.015
Gehalt2 * 0.015
Gehalt3 * 0.015
Gehalt4 * 0.015
...
```
Das ist erst einmal kein Problem. Jetzt möchte die Bank aber ihr Zinsen auf 2% erhöhen. Das müsste sie für jedes Gehalt einzeln tun:
```Python
Gehalt1 * 0.02
Gehalt2 * 0.02
Gehalt3 * 0.02
Gehalt4 * 0.02
...
```
Das wäre natürlich kein Problem, aber aufwändig. Aber spätestens wenn sich der Zinssatz regelmäßig erhöht, ist das kaum noch zu schaffen. Stattdessen nutzen Programmierer Variablen:
```Python
Zinsen = 0.015

Gehalt1 * Zinsen
Gehalt2 * Zinsen
Gehalt3 * Zinsen
Gehalt4 * Zinsen
...
```
Aber vielleicht ist dir bereits ein Problem aufgefallen: 
Wenn ich eine Rechnung `5 + 1` habe, was mache ich jetzt damit? \
Um etwas mit dem Ergebnis tun zu können, müssen wir es einfach ebenfalls wieder in einer Variable speichern. Dafür nutzen wir Ausdrücke (Expressions) \
Beispiel:
```Python
x = 5 + 1
```
Wobei der Teil nach dem `=` der Ausdruck ist. Zusammen nennt man den Inhalt dieser Zeile ein **Statement** ("Aussage").

### Datentypen
Datentypen sind ein wichtiger Bestandteil der Programmierung. Hier ist eine liste der allgemeinen, grundlegenden Datentypen (primitive datatypes):
| Typ    | Bedeutung                  |
|--------|----------------------------|
| int    | Ganzzahl (positiv/negativ) |
| uint   | Ganzzahl (nur positiv)     |
| float  | Dezimalzahl (wie 0.5)      |
| string | Text in `"text"`           |
| char   | Einzelnes Zeichen in `'A'` |

### Funktionen
Funktionen sind praktisch, um code sauber zu halten und sich nicht wiederholen zu müssen. Beispiel:
```Programmiersprache
Funktion addiere x und y:
    sage x + y
```
Du kannst mit Rückgabewerten auch arbeiten. Dazu speichern wir den Funktionsaufruf in einer Variable. \
Beispiel:
```Programmiersprache
Funktion addiere x und y:
    gib x + y zurück

ergebnis = addiere 10 und 3
```
Als code sähe das ungefär so aus:
```Python
def addiere(x, y):
    return x + y # return ist das englische Wort für "gib zurück"

ergebnis = addiere(10, 3)
```
Und mit dieser Einführung geht es jetzt zu Kapitel 2.

### Kommentare
**Kommentare** sind teile des Codes, die ignoriert werden. Sie sind praktisch für Dokumentation, Erklärungen und Übersichtlichkeit. \
Für die meisten Sprachen gilt: 
Zeilenkommentare werden mit einem `//` eingeleitet, Blockkomentare werden eingeleitet mit `/*` und beendet mit `*/`.
Es gibt aber auch ausnahmen: in manchen Sprachen sind Zeilenkommentare auch `#` oder werden mit einem ganz anderen Zeichen eingeleitet. 

## Python
**Python** ist eine dynamische Sprache, das heißt, der datentyp einer variable kann sich ändern. Es ist auf Einfachheit und Lesbarkeit ausgelegt.

### Blöcke (Scopes)
Blöcke sind in Python durch einen Doppelpunkt und Einrückung gekennzeichnet. \
Beispiel:
```
block:
    Alles was in diesem Bereich ist gehört zum block.
    Bei der Einrückung sollten immer 4 leerzeichen genutzt werden.
    Tabs sind nicht empfohlen und dürfen nicht mit leerzeichen gemischt werden.
```
### Variablen in Python
Variablen in Python sind wie bereits erklärt dynamisch. Man definiert eine Variable mit einer Zuweisung:
```Python
x = 5
```
Da Python eine dynamische Sprache ist, kann sich der Datentyp ändern:
```Python
x = 5 # jetzt ist x ein int
x = "text" # jetzt ist x ein string
x = 'c' # in python gibt es keinen char. x ist hier einfach ein string mit Länge 1
x = 5.6 # jetzt ist x ein float
```
### Funktionen in Python
Funktionen werden in Python mit dem Definitions-Keyword (Schlüsselwort) `def` eingeleitet. Darauf folgt der Name der Funktion und die Parameter in Klammern `()`, zuletzt der Doppelpunkt der das Scope einleitet. \
Beispiel:
```Python
def add(x, y):
    # Hier folgen deine Statements
```
Auch in Python können Funktionen Rückgabewerte haben:
```Python
def add(x, y):
    return x + y

x = add(5, 10) # x ist jetzt 15
```
### Die Standardbibliothek
Bevor wir fortfahren, brauchen wir ein paar grundlegende Funktionen aus der Standardbibliothek, das heißt Funktionen, die in die Sprache eingebaut sind. \
**Wichtig**: Vorraussetzung für diesen Abschnitt ist, dass du weißt was ein Terminal/Eine Konsole ist oder Abschnitt 7.1 [Die Konsole](#die-konsole) gelesen hast.
#### IO (Input/Output)
**IO Funktionen** sind Funktionen, die daten in dein Programm oder aus ihm raus befördern. Beispiel:
```Python
# print() schreibt alle parameter in die Konsole. Beispiel:
print("Hello, World") # Jetzt sollte 'Hello, World' bei dir in der Konsole erscheinen.

# input() nutzt erst print, um alle prameter in die Konsole auszugeben, um dann so lange zu warten, 
# bis der Nutzer etwas schreibt und Enter (neue Zeile) drückt. Die Eingabe des Nutzers wird dann zurückgegeben. Beispiel:
name = input("Dein Name: ")
```
Es gibt aber auch das sogenannte **File-IO** (Datei-IO). Dies sorgt dafür, dass du Dateien einlesen und Schreiben kannst.

###### Copyright (c) 2026 LuxUmbris (GitHub)
