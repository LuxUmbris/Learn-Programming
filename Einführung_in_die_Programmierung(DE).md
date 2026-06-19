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
   2.3 [Funktionen in Python](#funktionen-in-python) \
   2.4 [Die Standardbibliothek](#die-standardbibliothek) \
   2.5 [Bedingungen und Kontrollfluss](#bedingungen-und-kontrollfluss) \
   2.6 [Strings in Python](#strings-in-python)
3. [Andere Programmiersprachen](#andere-programmiersprachen)
4. [Einstieg in die Systemprogrammierung](#einstieg-in-die-systemprogrammierung)
5. [Einführung in C++](#einführung-in-c%2B%2B)
6. [Meine Sprache (C<<)](#meine-sprache)
7. [Installation und Nutzung von Werkzeugen](#installation-und-nutzung-von-werkzeugen)

---

## Grundlagen des Programmierens

### Variablen
Bestimmt kennst du das bereits aus dem Matheunterricht: Eine Variable ist in gewisser Weise ein Ersatz für einen Wert. Beispiel:

```python
x = 5
```

Und jetzt können wir diesen Wert für eine Rechnung nutzen:

```python
x + 2
```

Die Variable `x` ist `5`, was heißt, `x + 2` ist dasselbe wie `5 + 2`.

Jetzt fragst du dich sicher: Gut, aber wieso nutzen wir dann überhaupt Variablen? \
Ganz einfach: Stell dir vor, du hast eine Bank. Diese Bank gibt all ihren Klienten 1,5% Zinsen. Das sähe ungefähr so aus:

```python
Gehalt1 * 0.015
Gehalt2 * 0.015
Gehalt3 * 0.015
Gehalt4 * 0.015
...
```

Das ist erst einmal kein Problem. Jetzt möchte die Bank aber ihre Zinsen auf 2% erhöhen. Das müsste sie für jedes Gehalt einzeln tun:

```python
Gehalt1 * 0.02
Gehalt2 * 0.02
Gehalt3 * 0.02
Gehalt4 * 0.02
...
```

Das wäre zwar machbar, aber extrem aufwändig. Spätestens wenn sich der Zinssatz regelmäßig ändert, ist das kaum noch zu schaffen. Stattdessen nutzen Programmierer Variablen:

```python
Zinsen = 0.015

Gehalt1 * Zinsen
Gehalt2 * Zinsen
Gehalt3 * Zinsen
Gehalt4 * Zinsen
...
```

Aber vielleicht ist dir bereits ein Problem aufgefallen: Wenn ich eine Rechnung `5 + 1` habe, was mache ich jetzt damit? \
Um etwas mit dem Ergebnis tun zu können, müssen wir es einfach ebenfalls wieder in einer Variable speichern. Dafür nutzen wir Ausdrücke (Expressions).

Beispiel:
```python
x = 5 + 1
```
Wobei der Teil nach dem `=` der Ausdruck ist. Zusammen nennt man den Inhalt dieser Zeile ein **Statement** ("Aussage").

---

### Datentypen
Datentypen sind ein wichtiger Bestandteil der Programmierung. Hier ist eine Liste der allgemeinen, grundlegenden Datentypen (Primitive Datatypes):

| Typ | Bedeutung | Beispiel |
| :--- | :--- | :--- |
| **int** | Ganzzahl (positiv/negativ) | `5`, `-3` |
| **uint** | Ganzzahl (nur positiv) | `10` |
| **float** | Dezimalzahl | `0.5` |
| **string** | Text in Anführungszeichen | `"text"` |
| **char** | Einzelnes Zeichen in einfachen Anführungszeichen | `'A'` |
| **bool** | Wahrheitswert (wahr oder unwahr) | `True` oder `False` |

---

### Funktionen
Funktionen sind praktisch, um Code sauber zu halten und sich nicht wiederholen zu müssen. Beispiel:

```text
Funktion addiere x und y:
    sage x + y
```

Du kannst auch mit Rückgabewerten arbeiten. Dazu speichern wir den Funktionsaufruf in einer Variable.

Beispiel:
```text
Funktion addiere x und y:
    gib x + y zurück

ergebnis = addiere 10 und 3
```

Als echter Code sähe das ungefähr so aus:

```python
def addiere(x, y):
    return x + y # return ist das englische Wort für "gib zurück"

ergebnis = addiere(10, 3)
```
---

### Kommentare
**Kommentare** sind Teile des Codes, die vom Computer ignoriert werden. Sie sind praktisch für Dokumentation, Erklärungen und Übersichtlichkeit.

Für die meisten Sprachen gilt: Zeilenkommentare werden mit einem `//` eingeleitet, Blockkommentare werden eingeleitet mit `/*` und beendet mit `*/`.

Es gibt aber auch Ausnahmen: In manchen Sprachen (wie Python) sind Zeilenkommentare ein `#` oder werden mit einem ganz anderen Zeichen eingeleitet.

Und mit dieser Einführung geht es jetzt zu Kapitel 2.

---

## Python
**Python** ist eine dynamische Sprache, das heißt, der Datentyp einer Variable kann sich im Verlauf ändern. Sie ist auf Einfachheit und Lesbarkeit ausgelegt.

### Blöcke (Scopes)
Blöcke sind in Python durch einen Doppelpunkt und Einrückung gekennzeichnet.

Beispiel:
```text
block:
    Alles was in diesem Bereich ist, gehört zum Block.
    Bei der Einrückung sollten immer 4 Leerzeichen genutzt werden.
    Tabs sind nicht empfohlen und dürfen nicht mit Leerzeichen gemischt werden.
```

### Variablen in Python
Variablen in Python sind, wie bereits erklärt, dynamisch. Man definiert eine Variable einfach mit einer Zuweisung:

```python
x = 5
```

Da Python dynamisch ist, kann sich der Datentyp jederzeit ändern:

```python
x = 5       # Jetzt ist x ein int
x = "text"  # Jetzt ist x ein string
x = 'c'     # In Python gibt es keinen eigenen char-Typ. x ist hier einfach ein string mit der Länge 1
x = 5.6     # Jetzt ist x ein float
```

### Funktionen in Python
Funktionen werden in Python mit dem Definitions-Keyword (Schlüsselwort) `def` eingeleitet. Darauf folgt der Name der Funktion und die Parameter in Klammern `()`, zuletzt der Doppelpunkt, der den Scope einleitet.

Beispiel:
```python
def add(x, y):
    # Hier folgen deine Statements
    pass
```

Auch in Python können Funktionen Rückgabewerte haben:

```python
def add(x, y):
    return x + y

x = add(5, 10) # x ist jetzt 15
```

---

### Die Standardbibliothek
Bevor wir fortfahren, brauchen wir ein paar grundlegende Funktionen aus der Standardbibliothek – das heißt Funktionen, die fest in die Sprache eingebaut sind.

> **Wichtig:** Voraussetzung für diesen Abschnitt ist, dass du weißt, was ein Terminal oder eine Konsole ist, oder Abschnitt 7.1 [Die Konsole](#die-konsole) gelesen hast.

#### IO (Input/Output)
**IO-Funktionen** sind Funktionen, die Daten in dein Programm hinein oder aus ihm heraus befördern.

Beispiel:
```python
# print() schreibt alle Parameter in die Konsole. Beispiel:
print("Hello, World") # Jetzt sollte 'Hello, World' bei dir in der Konsole erscheinen.

# input() gibt zuerst den Text in die Konsole aus und wartet dann so lange, 
# bis der Nutzer etwas schreibt und Enter drückt. Die Eingabe wird dann zurückgegeben.
name = input("Dein Name: ")
```

Es gibt aber auch das sogenannte **File-IO** (Datei-IO). Dies sorgt dafür, dass du Dateien einlesen und schreiben kannst.

```python
# Datei öffnen:
with open("pfad/zur/datei", "r") as datei: 
    inhalt = datei.read()                  
```
> **Hinweis zum Modus:** `"r"` ist der Modus, um die Datei zu lesen. Die wichtigsten weiteren sind `"w"` (write/schreiben), `"a"` (append/anhängen) und `"x"` (exclusive creation/erzeugt die Datei und wirft einen Fehler, falls sie bereits vorhanden ist).
> 
> Das `with`-Keyword sorgt hierbei dafür, dass die Datei nach der Benutzung automatisch und sicher geschlossen wird, selbst wenn im Block ein Fehler passiert.

#### Erweiterte Funktionen
Die Standardbibliothek enthält auch weitere Module mit zusätzlichen Funktionen. Um diese nutzen zu können, brauchen wir `import`-Statements.

```python
import math
import random

x = math.sin(20)           # Sinus von 20
y = random.randint(0, 100) # Zufallszahl von 0 bis 100
```

Da die komplette Standardbibliothek den Rahmen dieser Einführung sprengen würde, ist hier nicht alles erklärt. Falls es dich interessiert, kannst du alle Informationen in der [offiziellen Python-Dokumentation](https://docs.python.org/3/library/index.html) finden.

---

### Bedingungen und Kontrollfluss

#### Bedingungen
Angenommen, du willst prüfen, ob der Nutzer eine Quizfrage richtig beantwortet hat. Dafür nutzen wir eine `if`-Condition (Falls-Bedingung) und den Vergleichsoperator `==`. Falls etwas zutrifft (`True`), tue etwas. Falls es nicht zutrifft (`False`), überspringe es.

Beispiel:
```python
print("Was ist die Hauptstadt von Frankreich?")
antwort = input(">> ")

if antwort.lower() == "paris": # Die Methode '.lower()' sorgt dafür, dass Großbuchstaben in Kleinbuchstaben umgewandelt werden
    print("Richtig!")
elif antwort.lower() == "berlin": # elif wird nur geprüft, wenn das vorherige 'if' nicht zugetroffen hat
    print("Frankreich ist nicht Deutschland!")
elif antwort.lower() == "london":
    print("Frankreich ist nicht das Vereinigte Königreich!")
else: # Falls keine der Bedingungen zutrifft
    print("Falsch.")
```
Kurze Übersicht der Booleischen Operatoren (True/False Operatoren):
* `==` True, wenn die Werte gleich sind
* `!=` True, wenn die Werte ungleich sind 
* `<` True, wenn der linke Wert kleiner als der Rechte ist
* `>` True, wenn der linke Wert größer als der Rechte ist
* `<=` True, wenn der linke Wert kleiner oder gleich dem Rechten ist
* `>=` True, wenn der linke Wert größer oder gleich dem Rechten ist
* `is` True, wenn das linke Objekt das rechte ist
* `not` True, wenn die folgende Bedingung False ist
* `or` True, wenn die linke oder rechte Bedingung True ist
* `and` True, wenn die linke UND die rechte Bedingung True sind
* `in` True, wenn der linke Wert im rechten Behälter vorhanden ist

#### Schleifen in Python
Es gibt zwei Arten von Schleifen:

**1. Die `while`-Schleife** \
Die `while`-Schleife tut so lange etwas, wie ihre Bedingung `True` ist oder bis sie auf ein `break` stößt.

Beispiel:
```python
x = 5
y = 7
while x < y:
    x += 1 # Ist dasselbe wie x = x + 1
    print(x)

while True: # Unendliche Schleife
    x += 1
    break # Bricht die Schleife sofort ab
```

**2. Die `for`-Schleife** \
`for`-Schleifen nutzt man vor allem, um etwas eine bestimmte Anzahl von Malen zu wiederholen oder Sammlungen zu durchlaufen:

```python
for _ in range(5): # Wiederhole 5-mal
    print("Wiederholung")

for i in range(5): # Wiederhole 5-mal und erhöhe den Zähler i jedes Mal um 1
    print("Wiederholung ", i)
```

#### Listen, Tupel und Dictionaries
Python unterstützt verschiedene Möglichkeiten, um mehrere Werte in einer einzigen Variable zu speichern:

* **Listen** `[ ]`: Sind veränderlich.
* **Tupel** `( )`: Sind unveränderlich (Konstanten).
* **Dictionaries** `{ }`: Speichern feste Paare (Schlüssel und Werte).

Beispiel für Listen und Tupel:
```python
meine_liste = [5, 7, 3, 9] # Eckige Klammern bedeuten Liste
mein_tupel = (5, 7, 3, 9)  # Runde Klammern bedeuten Tupel
```

Du kannst auf einen Wert in einer Liste zugreifen, indem du den sogenannten Index-Operator nutzt. Beim Programmieren beginnt man beim Zählen immer bei der Null. Das heißt, der erste Wert hat den Index `0`, der zweite den Index `1` usw.

Beispiel:
```python
x = [7, 3, 9, 65]
#    0  1  2  3

y = x[2] # Der Index 2 ist an der dritten Stelle, also 9
x[2] = 5 # Wir ändern den Wert an Index 2 zu 5. x ist jetzt: [7, 3, 5, 65]
```

Ein **Dictionary** wiederum enthält Schlüssel-Wert-Paare:
```python
mein_dict = {"banane": "obst", "tomate": "gemüse"}
```

Es gibt jede Menge eingebaute Funktionen und Methoden für Listen. Hier sind die wichtigsten:
```python
x = ["banane", "apfel"]

x.append("traube")    # Hängt "traube" an das Ende der Liste
x.insert(1, "orange") # Fügt "orange" am Index 1 der Liste ein
x.pop()               # Löscht das letzte Objekt der Liste
del x[0]              # Löscht das Objekt am Index 0
len(x)                # Gibt die Länge von x zurück
"apfel" in x          # Gibt True oder False zurück (ob das Element existiert)
```

Du kannst Listen und Tupel ziemlich praktisch in Schleifen verwenden:
```python
fruechte = ["banane", "apfel", "orange"]

for i in range(len(fruechte)): # Wir wiederholen für die Länge der Liste
    print("Frucht ", i, " ist ein(e) ", fruechte[i])

# Da for-Schleifen in Python direkt für Listen gemacht sind, 
# können wir das Ganze viel einfacher und schneller so schreiben:
i = 0
for frucht in fruechte:
    print("Frucht ", i, " ist ein(e) ", frucht)
    i += 1
```

---

### Strings in Python
Strings in Python kannst du dir vorstellen wie eine Art unveränderliche Liste, nur eben mit Zeichen.

Beispiel:
```python
x = "string"
print(x[3]) # Gibt 'i' aus
```

Du kannst wie bei Listen auch für Strings die Funktionen `len()` und den `in`-Operator verwenden.

#### Die wichtigsten String-Typen
1. **f-Strings** (Format-Strings): Sie bekommen das Präfix `f` vorangestellt. Ab dann werden Variablennamen innerhalb geschweifter Klammern direkt durch ihren Wert ersetzt.
```python
pizzas = 5
print(f"Ich habe {pizzas} Pizzas bestellt!")
```

2. **Mehrzeilige Strings**: Nutzen dreifache Anführungszeichen.
```python
nachricht = """Hallo Frau X,
ich wollte Ihnen dafür danken, dass...
Liebe Grüße,
Ihr Y"""
```

---

### Das Modulsystem in Python
Python hat ein Modulsystem. Das heißt, du kannst dein Projekt auf mehrere Dateien verteilen, um die Übersicht zu wahren. Jede Python-Datei hat die Endung `.py`.

Nutzung:
```python
import meine_datei # .py Endung beim Import weglassen!

meine_datei.add(6, 8) # Angenommen, die Funktion wurde in der Datei meine_datei.py definiert
```

#### Der Einstiegspunkt
Der Einstiegspunkt ist in Python immer die direkt ausgeführte Datei. Diese wird von oben nach unten Zeile für Zeile abgearbeitet:

```python
print("Dies kommt zuerst")
print("Dies kommt als zweites")
```

Das oben Gezeigte nennt man **globalen Code** oder auch **Top-Level-Code**. Du solltest versuchen, globalen Code für Logik zu vermeiden. Er gilt nicht nur als unsauber, sondern wird auch sofort automatisch ausgeführt, sobald du ein Modul importierst. 

Dafür definiert man stattdessen eine Hauptfunktion, die sogenannte `main`-Funktion, und führt diese nur aus, wenn man sich aktiv in der dazugehörigen Hauptdatei befindet:

```python
def main(): # Wir definieren den Einstiegspunkt
    print("Hello, World!")

if __name__ == "__main__": # Prüft, ob diese Datei direkt ausgeführt wurde
    main() # Führt die main-Funktion aus
```

---
## Einführung in die Systemprogrammierung
Um den Unterschied zwischen einer Hochsprache und einer Systemsprache zu verstehen, muss man zunächst den Untschied zwischen einem Interpreter und einem Compiler vestehen. Ein Interpreter ließt dein Programm Zeile für Zeile und führt es aus, wärend ein Compiler dein Programm in Maschinencode umwandelt, den dein Computer dann direkt versteht. Es gibt auch Hybride ("VM-Sprachen") wie Java, bei denen der Quellcode erst zu einem optimierten, sogenannten "Java-Bytecode" kompiliert, und dann interpretiert wird. \
Vor- und Nachteile im Vergleich:

| Compiler | Interpreter |
|----------|-------------|
| Programm muss vorher umgewandelt werden | Programm kann direkt ausgefüht werden |
| Hohe Performance des Programms | Schlechtere Performance des Programms |
| Nutzer braucht nur das Programm | Nutzer muss den Interpreter installiert haben |
| Programm kann vorher lange optimiert werden | Programm muss schnell ausgeführt werden |

---

### Speichermanagement
Wenn du eine Variable definierst, verbrauchst du damit physischen Platz auf deiner CPU (Zentaralen Recheneinheit) oder im RAM (Arbeitsspeicher). In Hochsprachen wie Python wird dafür oft ein sogenannter GC (Garbage-Collector/"Müllsammler") Genutzt. Dieser pausiert die komplette Ausführung des Programms und gibt ungenutzten Platz wieder frei. Dies kostet aber wie beschrieben wertvolle Ausführungszeit. Deswegen gibt es Sprachen mit manueller Speicherverwaltung. Dies ist allerdings extrem fehleranfällig. Wieder andere Sprachen geben Variablen immer am Ende von Scopes frei.

---

### Die Statische Typisierung
Anders als in dynamischen Sprachen wie Python sind Variablen in der Systemprogrammierung meist statisch, das heißt sie können ihren Datentyp nach dem definieren nicht mehr ändern. Auch Funktionen müssen angeben, welchen Datentyp ihr zurückgegebener Wert hat.

---

###### Copyright (c) 2026 LuxUmbris (GitHub)
