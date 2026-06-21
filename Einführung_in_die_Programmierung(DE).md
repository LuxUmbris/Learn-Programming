# Einstieg in die Programmierung
###### Document version: 1.0.0 (DE)

Dies ist eine grundlegende Einführung in die Programmierung. Sie enthält:

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
3. [Einstieg in die Systemprogrammierung](#einstieg-in-die-systemprogrammierung) \
   3.1 [Speicherverwaltung](#speicherverwaltung)\
   3.2 [Die statische Typisierung](#die-statische-typisierung)
4. [Einstieg in C++](#einstieg-in-c) \
4.1 [Variablen in C++](#variablen-in-c) \
4.2 [Bedingungen und Kontrollfluss in C++](#bedingungen-und-kontrollfluss-in-c) \
4.3 [Funktionen in C++](#funktionen-in-c) \
4.4 [Strings in C++](#strings-in-c) \
4.5 [Die C++ Standardbibliothek](#die-c-standardbibliothek) \
4.6 [Container in C++](#container-in-c) \
4.7 [Datei-IO in C++](#datei-io-in-c) \
4.8 [Pointer](#pointer) \
4.9 [Structs in C++](#structs-in-c) \
4.10 [Ein C++ Programm kompilieren](#ein-c-programm-kompilieren) \
4.11 [OOP und DOD](#oop-und-dod) \
4.12 [Meine Art, C++ zu schreiben](#meine-art-c-zu-schreiben)
5. [Einstieg in meine Sprache (C<<)](#einstieg-in-meine-sprache-c) \
5.1 [Der Einstiegspunkt](#der-einstiegspunkt) \
5.2 [Variablen und Typen](#variablen-und-typen) \
5.3 [Funktionen und Tunnel](#funktionen-und-tunnel) \
5.4 [Kontrollfluss](#kontrollfluss) \
5.5 [Das Arena-Modell (Speicherverwaltung)](#das-arena-modell-speicherverwaltung) \
5.6 [Der "Voided State" und move](#der-voided-state-und-move) \
5.7 [Arrays und Container](#arrays-und-container) \
5.8 [Structs, Enums und Zero-Cost Classes](#structs-enums-und-zero-cost-classes) \
5.9 [Imports und C-Interop](#imports-und-c-interop) \
5.10 [Die Standardbibliothek (`std`)](#die-standardbibliothek-std) \
5.11 [Ein vollständiges Beispiel](#ein-vollständiges-beispiel) \
5.12 [Der Weg zu 1.0: Self-Hosting](#der-weg-zu-10-self-hosting)
6. [Tools und Installation](#tools-und-installation) \
6.1 [Das Terminal](#das-terminal) \
6.2 [Grundlegende Bash-Befehle](#grundlegende-bash-befehle) \
6.3 [WSL (Windows Subsystem for Linux)](#wsl-windows-subsystem-for-linux) \
6.4 [VS Code installieren und mit WSL nutzen](#vs-code-installieren-und-mit-wsl-nutzen) \
6.5 [Git und GitHub CLI (gh)](#git-und-github-cli-gh) \
6.6 [SSH](#ssh) \
6.7 [Archive: zip und xz](#archive-zip-und-xz) \
6.8 [Python installieren](#python-installieren) \
6.9 [C++ Compiler installieren (clang++ / g++)](#c-compiler-installieren-clang-g) \
6.10 [gdb – der Debugger](#gdb-der-debugger) \
6.11 [Den C<< Compiler (cshift) installieren](#den-c-compiler-cshift-installieren)

---

## Grundlagen des Programmierens

### Variablen
Bestimmt kennst du das bereits aus dem Matheunterricht: Eine Variable ist in gewisser Weise ein Platzhalter für einen Wert. Beispiel:

```python
x = 5
```

Und jetzt können wir diesen Wert für eine Rechnung nutzen:

```python
x + 2
```

Die Variable `x` steht für `5`, was bedeutet, dass `x + 2` dasselbe ist wie `5 + 2`.

Jetzt fragst du dich sicher: Gut, aber wieso nutzen wir dann überhaupt Variablen? \
Ganz einfach: Stell dir vor, du betreibst eine Bank. Diese Bank gibt all ihren Kunden 1,5% Zinsen. Im Code sähe das ungefähr so aus:

```python
Gehalt1 * 0.015
Gehalt2 * 0.015
Gehalt3 * 0.015
Gehalt4 * 0.015
...
```

Das ist erst einmal kein Problem. Jetzt möchte die Bank aber ihre Zinsen auf 2% erhöhen. Das müsste sie für jedes Gehalt einzeln anpassen:

```python
Gehalt1 * 0.02
Gehalt2 * 0.02
Gehalt3 * 0.02
Gehalt4 * 0.02
...
```

Das wäre zwar machbar, aber extrem aufwändig. Spätestens wenn sich der Zinssatz regelmäßig ändert, ist das kaum noch zu bewältigen. Stattdessen nutzen Programmierer Variablen:

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
Wobei der Teil nach dem `=` der Ausdruck ist. Zusammen nennt man den Inhalt dieser Zeile ein **Statement** ("Anweisung").

---

### Datentypen
Datentypen sind ein fundamentaler Bestandteil der Programmierung. Hier ist eine Liste der allgemeinen, grundlegenden Datentypen (Primitive Datatypes):

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
Funktionen sind praktisch, um Code übersichtlich zu halten und Wiederholungen zu vermeiden. Beispiel:

```text
Funktion addiere x und y:
    sage x + y
```

Du kannst auch mit Rückgabewerten arbeiten. Dazu speichern wir das Ergebnis des Funktionsaufrufs in einer Variable.

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
**Kommentare** sind Teile des Codes, die vom Computer beim Ausführen ignoriert werden. Sie sind praktisch für Dokumentation, Erklärungen und die Übersichtlichkeit.

Für die meisten Sprachen gilt: Zeilenkommentare werden mit einem `//` eingeleitet, Blockkommentare werden mit `/*` begonnen und mit `*/` beendet.

Es gibt aber auch Ausnahmen: In manchen Sprachen (wie Python) werden Zeilenkommentare durch ein `#` oder ein ganz anderes Zeichen eingeleitet.

Und mit dieser Einführung geht es jetzt zu Kapitel 2.

---

## Python
**Python** ist eine dynamisch typisierte Sprache. Das heißt, der Datentyp einer Variable kann sich im Verlauf des Programms ändern. Sie ist besonders auf Einfachheit und Lesbarkeit ausgelegt.

### Blöcke (Scopes)
Blöcke werden in Python durch einen Doppelpunkt und anschließende Einrückung gekennzeichnet.

Beispiel:
```text
block:
    Alles, was in diesem Bereich eingerückt ist, gehört zum Block.
    Bei der Einrückung sollten immer 4 Leerzeichen genutzt werden.
    Tabs sind nicht empfohlen und dürfen nicht mit Leerzeichen gemischt werden.
```

### Variablen in Python
Variablen in Python sind, wie bereits erklärt, dynamisch. Man definiert eine Variable einfach durch eine Zuweisung:

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
Funktionen werden in Python mit dem Schlüsselwort (Keyword) `def` eingeleitet. Darauf folgt der Name der Funktion und die Parameter in Klammern `()`, gefolgt von einem Doppelpunkt, der den Scope einleitet.

Beispiel:
```python
def add(x, y):
    # Hier folgen deine Statements
    pass
```

Auch in Python können Funktionen Rückgabewerte besitzen:

```python
def add(x, y):
    return x + y

x = add(5, 10) # x ist jetzt 15
```

---

### Die Standardbibliothek
Bevor wir fortfahren, brauchen wir ein paar grundlegende Funktionen aus der Standardbibliothek – das heißt Funktionen, die bereits fest in die Sprache eingebaut sind.

> **Wichtig:** Voraussetzung für diesen Abschnitt ist, dass du weißt, was ein Terminal oder eine Konsole ist, oder bereits Abschnitt 6.1 [Das Terminal](#das-terminal) gelesen hast.

#### IO (Input/Output)
**IO-Funktionen** sind Funktionen, die Daten in dein Programm hinein- oder aus ihm herausbefördern.

Beispiel:
```python
# print() schreibt alle Parameter in die Konsole. Beispiel:
print("Hello, World") # Jetzt sollte 'Hello, World' bei dir in der Konsole erscheinen.

# input() gibt zuerst den Text in die Konsole aus und wartet dann so lange, 
# bis der Nutzer etwas eingibt und Enter drückt. Die Eingabe wird dann zurückgegeben.
name = input("Dein Name: ")
```

Es gibt aber auch das sogenannte **File-IO** (Datei-IO). Dieses sorgt dafür, dass du Dateien einlesen und beschreiben kannst.

```python
# Datei öffnen:
with open("pfad/zur/datei", "r") as datei: 
    inhalt = datei.read()                  
```
> **Hinweis zum Modus:** `"r"` ist der Modus, um die Datei zu lesen (read). Die wichtigsten weiteren sind `"w"` (write/schreiben), `"a"` (append/anhängen) und `"x"` (exclusive creation/erzeugt die Datei und wirft einen Fehler, falls sie bereits existiert).
> 
> Das `with`-Keyword sorgt hierbei dafür, dass die Datei nach der Benutzung automatisch und sicher geschlossen wird, selbst wenn innerhalb des Blocks ein Fehler auftritt.

#### Erweiterte Funktionen
Die Standardbibliothek enthält auch weitere Module mit zusätzlichen Funktionen. Um diese nutzen zu können, benötigen wir `import`-Statements.

```python
import math
import random

x = math.sin(20)           # Sinus von 20
y = random.randint(0, 100) # Zufallszahl von 0 bis 100
```

Da die komplette Standardbibliothek den Rahmen dieser Einführung sprengen würde, wird hier nicht alles erklärt. Falls es dich interessiert, findest du alle Informationen in der [offiziellen Python-Dokumentation](https://docs.python.org/3/library/index.html).

---

### Bedingungen und Kontrollfluss

#### Bedingungen
Angenommen, du willst prüfen, ob ein Nutzer eine Quizfrage richtig beantwortet hat. Dafür nutzen wir eine `if`-Condition (Falls-Bedingung) und den Vergleichsoperator `==`. Falls die Bedingung zutrifft (`True`), wird der Code ausgeführt. Falls sie nicht zutrifft (`False`), wird er übersprungen.

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
Kurze Übersicht der booleschen Operatoren (True/False Operatoren):
* `==` True, wenn die Werte gleich sind
* `!=` True, wenn die Werte ungleich sind 
* `<` True, wenn der linke Wert kleiner als der rechte ist
* `>` True, wenn der linke Wert größer als der rechte ist
* `<=` True, wenn der linke Wert kleiner oder gleich dem rechten ist
* `>=` True, wenn der linke Wert größer oder gleich dem rechten ist
* `is` True, wenn das linke Objekt identisch mit dem rechten ist
* `not` True, wenn die folgende Bedingung False ist
* `or` True, wenn die linke oder die rechte Bedingung True ist
* `and` True, wenn die linke UND die rechte Bedingung True sind
* `in` True, wenn der linke Wert im rechten Datentopf vorhanden ist

> WICHTIG: Der Vergleichsoperator `==` ist NICHT das selbe wie `is`. Du kannst dir das so vorstellen:
> Du hast eine Katze. Diese klonst du. Jetzt hast du zwar zwei identische Katzen, aber sie sind nicht die selbe Katze. Ein `==` würde hier sagen, dass ist `True`, weil die Katzen identisch sind. `is` würde sagen es ist `False`, weil es nicht die selbe Katze ist. Jetzt fragst du dich:
> Gut, aber wozu brauche ich das jetzt, ich weiß doch dass x eben x ist!
> Ja, das stimmt. Aber: In Python sind Werte wie None, True und False eben keine Werte, sondern Objekte. Bei ihnen solltest du immer `is` nutzen, denn wenn etwas `True` ist, dann verweist es eigentlich nur auf das Objekt namens `True`.

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
`for`-Schleifen nutzt man vor allem, um Aktionen eine bestimmte Anzahl von Malen zu wiederholen oder um Sammlungen zu durchlaufen:

```python
for _ in range(5): # Wiederhole 5-mal
    print("Wiederholung")

for i in range(5): # Wiederhole 5-mal und erhöhe den Zähler i jedes Mal um 1
    print("Wiederholung ", i)
```

#### Listen, Tupel und Dictionaries
Python unterstützt verschiedene Möglichkeiten, um mehrere Werte in einer einzigen Variable zu speichern:

* **Listen** `[ ]`: Sind veränderlich (mutable).
* **Tupel** `( )`: Sind unveränderlich (immutable / Konstanten).
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

y = x[2] # Der Index 2 steht an der dritten Stelle, also 9
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
x.pop()               # Entfernt das letzte Objekt der Liste
del x[0]              # Löscht das Objekt am Index 0
len(x)                # Gibt die Länge von x zurück
"apfel" in x          # Gibt True oder False zurück (ob das Element existiert)
```

Du kannst Listen und Tupel ziemlich praktisch in Schleifen verwenden:
```python
fruechte = ["banane", "apfel", "orange"]

for i in range(len(fruechte)): # Wir wiederholen für die Länge der Liste
    print("Frucht ", i, " ist ein(e) ", fruechte[i])

# Da for-Schleifen in Python direkt für Listen optimiert sind, 
# können wir das Ganze viel einfacher und schneller so schreiben:
i = 0
for frucht in fruechte:
    print("Frucht ", i, " ist ein(e) ", frucht)
    i += 1
```

---

### Strings in Python
Strings in Python kannst du dir vorstellen wie eine Art unveränderliche Liste, nur eben bestehend aus Zeichen.

Beispiel:
```python
x = "string"
print(x[3]) # Gibt 'i' aus
```

Du kannst wie bei Listen auch für Strings die Funktion `len()` und den `in`-Operator verwenden.

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
Python besitzt ein Modulsystem. Das heißt, du kannst dein Projekt auf mehrere Dateien verteilen, um die Übersicht zu wahren. Jede Python-Datei hat die Endung `.py`.

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
Um den Unterschied zwischen einer Hochsprache und einer Systemsprache zu verstehen, muss man zunächst den Unterschied zwischen einem Interpreter und einem Compiler nachvollziehen. Ein Interpreter liest dein Programm Zeile für Zeile und führt es direkt aus, während ein Compiler dein Programm vorab in Maschinencode umwandelt, den dein Computer dann direkt versteht. Es gibt auch Hybride ("VM-Sprachen") wie Java, bei denen der Quellcode erst zu einem optimierten, sogenannten "Java-Bytecode" kompiliert und anschließend interpretiert wird. \
Vor- und Nachteile im Vergleich:

| Compiler | Interpreter |
|----------|-------------|
| Programm muss vorher umgewandelt werden | Programm kann direkt ausgeführt werden |
| Hohe Performance des Programms | Schlechtere Performance des Programms |
| Nutzer braucht nur das Programm | Nutzer muss den Interpreter installiert haben |
| Programm kann vorher lange optimiert werden | Programm muss schnell ausgeführt werden |

---

### Speicherverwaltung
Wenn du eine Variable definierst, verbrauchst du damit physischen Platz auf deiner CPU (Zentralen Recheneinheit) oder im RAM (Arbeitsspeicher). In Hochsprachen wie Python wird dafür oft ein sogenannter GC (Garbage-Collector / "Müllsammler") genutzt. Dieser pausiert die komplette Ausführung des Programms und gibt ungenutzten Speicherplatz wieder frei. Dies kostet jedoch wertvolle Ausführungszeit. Deswegen gibt es Sprachen mit manueller Speicherverwaltung. Diese ist allerdings extrem fehleranfällig. Wieder andere Sprachen geben Variablen immer automatisch am Ende von Scopes frei.

---

### Die statische Typisierung
Anders als in dynamischen Sprachen wie Python sind Variablen in der Systemprogrammierung meist statisch typisiert. Das heißt, sie können ihren Datentyp nach dem Definieren nicht mehr ändern. Auch Funktionen müssen im Vorfeld angeben, welchen Datentyp ihr zurückgegebener Wert hat.

---

## Einstieg in C++
**C++** ist, im Gegensatz zu Python, eine kompilierte und statisch typisierte Sprache. Das heißt: Bevor dein Programm läuft, übersetzt ein Compiler deinen Code in Maschinencode, und jede Variable hat ab ihrer Definition einen festen Datentyp, der sich nicht mehr ändert.

C++ baut auf der Sprache C auf und erweitert sie unter anderem um Klassen, Templates und eine umfangreiche Standardbibliothek. Wie du später im Abschnitt [Meine Art, C++ zu schreiben](#meine-art-c-zu-schreiben) siehst, nutze ich davon bewusst nur einen kleinen, aber soliden Teil. Dieses Kapitel geht trotzdem etwas tiefer als das Python-Kapitel – C++ verlangt dir an mehr Stellen ab, selbst zu entscheiden, wie etwas gemacht wird, und genau diese Stellen solltest du einmal bewusst gesehen haben.

### Variablen in C++
Da C++ statisch typisiert ist, musst du den Datentyp einer Variable bei der Definition angeben:

```cpp
int x = 5;
float y = 3.14f;
char c = 'A';
bool flag = true;
std::string text = "Hallo";
```

Anders als in Python gibt es hier keine Einrückung mit Doppelpunkt, sondern geschweifte Klammern `{ }`, die einen Block (Scope) öffnen und schließen. Jede Anweisung wird außerdem mit einem Semikolon `;` beendet.

Ein minimales C++ Programm sieht so aus:
```cpp
int main() {
    int x = 5;
    return 0; // 0 bedeutet "Programm erfolgreich beendet"
}
```
`main` ist, genau wie in Python die `if __name__ == "__main__"`-Prüfung, der Einstiegspunkt deines Programms.

Eine Variable kannst du außerdem mit `const` als unveränderlich markieren – ein Versuch, sie danach zu ändern, ist dann bereits ein Compilerfehler:
```cpp
const float pi = 3.14159f;
// pi = 3.0; // [FEHLER] assignment of read-only variable 'pi'
```

---

### Bedingungen und Kontrollfluss in C++
Bedingungen funktionieren im Prinzip wie in Python, nur mit anderer Syntax: Statt Doppelpunkt und Einrückung nutzt C++ runde Klammern um die Bedingung und geschweifte Klammern für den Block.

```cpp
int antwort = 7;

if (antwort == 7) {
    std::cout << "Richtig!" << std::endl;
} else if (antwort < 7) {
    std::cout << "Zu niedrig!" << std::endl;
} else {
    std::cout << "Zu hoch!" << std::endl;
}
```

Die Vergleichs- und logischen Operatoren entsprechen denen aus Python, nur mit anderen Symbolen für "und"/"oder"/"nicht":

| Operator | Bedeutung |
| :--- | :--- |
| `==` / `!=` | gleich / ungleich |
| `<` `>` `<=` `>=` | kleiner / größer (oder gleich) |
| `&&` | und (statt `and`) |
| `\|\|` | oder (statt `or`) |
| `!` | nicht (statt `not`) |

#### Schleifen
Auch hier gibt es `while` und `for`, allerdings mit einer klassischeren `for`-Syntax als in Python:

```cpp
int i = 0;
while (i < 5) {
    std::cout << i << std::endl;
    i++; // Kurzform für i += 1
}

for (int i = 0; i < 5; i++) {
    std::cout << i << std::endl;
}
```
Die drei Teile in den `for`-Klammern sind: Startwert, Abbruchbedingung, Schritt nach jedem Durchlauf – das ist mächtiger, aber auch weniger "lesbar auf den ersten Blick" als Pythons `for i in range(5)`.

`switch` ist die C++-Variante von langen `elif`-Ketten, wenn du eine Variable gegen viele feste Werte prüfen willst:
```cpp
switch (note) {
    case 1:
        std::cout << "Sehr gut" << std::endl;
        break; // Ohne break "fällt" der Code in den nächsten case durch
    case 2:
        std::cout << "Gut" << std::endl;
        break;
    default:
        std::cout << "Unbekannte Note" << std::endl;
}
```

---

### Funktionen in C++
Funktionen brauchen in C++ zusätzlich zum Namen und den Parametern auch einen Rückgabetyp:

```cpp
int add(int x, int y) {
    return x + y;
}

int main() {
    int ergebnis = add(10, 3);
    return 0;
}
```

Falls eine Funktion nichts zurückgibt, nutzt du den Typ `void`:
```cpp
void sage_hallo() {
    std::cout << "Hallo!" << std::endl;
}
```

Parameter können auch **Standardwerte** bekommen, die nur greifen, wenn beim Aufruf nichts übergeben wird:
```cpp
void begruessen(std::string name = "Welt") {
    std::cout << "Hallo, " << name << "!" << std::endl;
}

begruessen();          // Hallo, Welt!
begruessen("Vincent"); // Hallo, Vincent!
```

---

### Strings in C++
`std::string` (aus `<string>`) ist der Stringtyp in C++. Anders als in Python sind Strings hier **veränderlich** (mutable):

```cpp
#include <string>

std::string name = "Vincent";
std::string gruss = "Hallo, " + name + "!"; // Strings lassen sich mit + verbinden

std::cout << gruss.length() << std::endl;     // Länge des Strings
std::cout << gruss[0] << std::endl;            // Index-Zugriff, wie bei Listen
std::cout << gruss.substr(7, 7) << std::endl;  // Teilstring: ab Index 7, Länge 7
```

Weitere wichtige Methoden:
```cpp
std::string s = "Hello, World";
s.find("World");       // Index, an dem "World" beginnt (std::string::npos, wenn nicht gefunden)
s.replace(0, 5, "Hi");  // Ersetzt 5 Zeichen ab Index 0 durch "Hi"
s.append("!");          // Hängt "!" an
```

Für f-String-ähnliches Zusammensetzen von Text und Zahlen nutzt man `std::stringstream` aus `<sstream>`:
```cpp
#include <sstream>

int pizzas = 5;
std::stringstream ss;
ss << "Ich habe " << pizzas << " Pizzas bestellt!";
std::string ergebnis = ss.str();
```

---

### Die C++ Standardbibliothek
Auch C++ bringt eine Standardbibliothek mit. Eingebunden werden ihre Teile über `#include`-Direktiven am Dateianfang. Hier die wichtigsten, die du am Anfang wirklich brauchst:

| Header | Wofür |
| :--- | :--- |
| `<iostream>` | Ein- und Ausgabe über die Konsole (`std::cout`, `std::cin`) |
| `<fstream>` | Datei-IO (Dateien lesen/schreiben) |
| `<sstream>` | String-Streams, z. B. um Zahlen und Text zusammenzusetzen |
| `<string>` | Der `std::string`-Datentyp für Texte |
| `<cmath>` | Mathematische Funktionen (`sqrt`, `sin`, `pow`, ...) |
| `<algorithm>` | Fertige Algorithmen wie `sort`, `find`, `min`, `max` |
| `<vector>` | Der `std::vector`-Container (siehe nächster Abschnitt) |

Beispiel:
```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```
`std::` ist hierbei ein sogenannter Namespace. Er sorgt dafür, dass z. B. `cout` aus der Standardbibliothek nicht mit einer eigenen Variable namens `cout` kollidiert.

Über `std::cin` kannst du, analog zu Pythons `input()`, auch Eingaben einlesen:
```cpp
std::string eingabe;
std::cout << "Dein Name: ";
std::cin >> eingabe; // liest bis zum nächsten Leerzeichen/Zeilenumbruch
```

---

### Container in C++
Ein Container ist, ähnlich wie eine Liste in Python, ein Datentyp, der mehrere Werte speichert. Der wichtigste und am häufigsten genutzte ist `std::vector` (ein dynamisches Array):

```cpp
#include <vector>

std::vector<int> zahlen = {1, 2, 3, 4};
zahlen.push_back(5); // Hängt 5 ans Ende an

for (int zahl : zahlen) { // "Range-based for", ähnlich wie 'for x in liste' in Python
    std::cout << zahl << std::endl;
}
```

Die spitzen Klammern `<int>` geben an, welchen Datentyp der Vector enthält. Auch `std::string` lässt sich übrigens wie ein Container aus einzelnen `char`s behandeln, inklusive Index-Zugriff (`text[0]`) und `.size()`.

`<algorithm>` liefert fertige Operationen, die direkt auf Containern arbeiten, zum Beispiel Sortieren:
```cpp
#include <algorithm>

std::vector<int> zahlen = {5, 3, 9, 1};
std::sort(zahlen.begin(), zahlen.end()); // zahlen ist jetzt {1, 3, 5, 9}
```
`begin()` und `end()` sind sogenannte **Iteratoren** – sie markieren Anfang und Ende des Bereichs, auf den die Funktion angewendet werden soll. Nach demselben Prinzip funktionieren z. B. auch `std::find`, `std::min_element` und `std::max_element`.

---

### Datei-IO in C++
Genau wie in Python (`with open(...)`) kannst du auch in C++ Dateien lesen und schreiben, über `<fstream>`:

```cpp
#include <fstream>
#include <string>

// Schreiben
std::ofstream out("pfad/zur/datei.txt");
out << "Hallo, Datei!" << std::endl;

// Lesen, Zeile für Zeile
std::ifstream in("pfad/zur/datei.txt");
std::string zeile;
while (std::getline(in, zeile)) {
    std::cout << zeile << std::endl;
}
```
`std::ofstream` ("output file stream") schreibt, `std::ifstream` ("input file stream") liest. Ein explizites `.close()` brauchst du normalerweise nicht: Dank RAII (siehe nächster Abschnitt) schließen beide die Datei automatisch, sobald sie ihren Scope verlassen.

---

### Pointer
Ein **Pointer** speichert keine Werte direkt, sondern die Speicheradresse eines anderen Werts. Das ist die Grundlage von Systemprogrammierung in C++.

```cpp
int x = 5;
int* p = &x;  // p zeigt jetzt auf die Adresse von x
*p = 10;      // Über den Pointer ändern wir den Wert von x. x ist jetzt 10
```

* `&x` gibt die Adresse von `x` zurück.
* `*p` greift auf den Wert zu, auf den `p` zeigt ("dereferenzieren").

Pointer sind mächtig, aber auch fehleranfällig: Vergisst du, Speicher freizugeben, hast du ein **Memory Leak**. Greifst du auf ungültige Adressen zu, stürzt dein Programm ab.

Genau hier kommt **RAII** (*Resource Acquisition Is Initialization*) ins Spiel: Statt Speicher manuell mit `new`/`delete` zu verwalten, bindest du ihn an die Lebenszeit eines Objekts. `std::string`, `std::vector` und `std::fstream` machen das bereits automatisch für dich – sobald sie ihren Scope verlassen, geben sie ihren Speicher selbstständig frei. Das ist der Grund, warum ich in meinem eigenen Code praktisch nie `new` oder `delete` von Hand schreibe.

---

### Structs in C++
Ein `struct` bündelt mehrere Werte unter einem Namen – reine Daten, ohne Methoden. Das ist das zentrale Werkzeug, um Daten zu strukturieren, ohne gleich eine Klasse zu bauen:

```cpp
struct Spieler {
    std::string name;
    int gesundheit;
    float x, y;
};

Spieler p;
p.name = "Vincent";
p.gesundheit = 100;
p.x = 0.0f;
p.y = 0.0f;

p.gesundheit -= 30; // Schaden nehmen
```

Mit `std::vector<Spieler>` lassen sich dann ganze Gruppen von Daten zusammenhängend im Speicher halten – genau das Prinzip aus dem Abschnitt [OOP und DOD](#oop-und-dod):
```cpp
std::vector<Spieler> spieler;
spieler.push_back(p);

for (Spieler& s : spieler) { // & sorgt dafür, dass wir die echten Objekte ändern, nicht Kopien
    s.gesundheit -= 5;
}
```

---

### Ein C++ Programm kompilieren
Im Gegensatz zu Python (`python3 datei.py`) musst du ein C++ Programm zuerst kompilieren, bevor du es ausführen kannst. Mit dem Compiler aus [Tools und Installation](#c-compiler-installieren-clang-g):

```bash
g++ programm.cpp -o programm   # Kompilieren
./programm                     # Ausführen (unter Windows ohne WSL: programm.exe)
```

`-o programm` legt fest, wie die erzeugte ausführbare Datei heißen soll. Ohne diese Option würde der Compiler eine Datei namens `a.out` erzeugen.

---

### OOP und DOD
**OOP** (*Object-Oriented Programming*) bündelt Daten und die dazugehörigen Funktionen (Methoden) in Klassen. Über Vererbung und Polymorphismus lassen sich Hierarchien von Objekten bauen, die sich "wie echte Dinge" verhalten.

**DOD** (*Data-Oriented Design*) denkt andersherum: Statt Daten in einzelne Objekte zu verpacken, hält man gleichartige Daten zusammenhängend im Speicher (z. B. in einem `std::vector`) und verarbeitet sie in Stapeln. Der Grund: Moderne CPUs sind extrem schnell darin, zusammenhängenden Speicher zu lesen ("Cache Locality"), aber langsam darin, wild verstreuten Objekten über Pointer hinterherzujagen ("Pointer Chasing"). Genau das passiert aber häufig bei tiefen Klassenhierarchien.

Kurz gesagt:
* OOP optimiert dafür, wie ein Mensch über Probleme nachdenkt (Objekte, Hierarchien).
* DOD optimiert dafür, wie die Hardware tatsächlich arbeitet (Speicherlayout, Cache).

Für UI-lastigen oder stark modellierten Code kann OOP weiterhin sinnvoll sein. Für performancekritischen System-Code – Compiler, Engines, Simulationen – ist DOD in aller Regel sauberer, vorhersehbarer und schneller.

---

### Meine Art, C++ zu schreiben
Wenn ich C++ schreibe, sieht man bei mir so gut wie keine eigenen Klassen. Mein Stil lässt sich am besten so zusammenfassen: **"C with Classes" – aber ohne die Classes.**

Konkret heißt das: Ich nutze fast ausschließlich diese Werkzeuge aus der Standardbibliothek:
* `<string>`, `<sstream>` – für Text
* `<cmath>` – für Mathematik
* `<algorithm>` – für fertige, getestete Algorithmen
* `<iostream>`, `<fstream>` – für Ein-/Ausgabe und Dateien
* `<vector>` – als praktisch einziger Container
* `struct` – um Daten zu bündeln, wo es nötig ist
* RAII – statt manuellem Speichermanagement

Das ist absichtlich eine kleine Liste. Und genau das ist die Botschaft, die ich euch mitgeben will: Es gibt gar nicht so viele komplexe Dinge, die man wirklich beherrschen muss, um produktiv und sauber zu programmieren. Eigene Klassenhierarchien, Mehrfachvererbung, Operator-Overloading, Exceptions – das alles klingt nach "richtigem C++", erzeugt in der Praxis aber oft nur Overhead, versteckte Kosten und schwer nachvollziehbaren Code.

Ein typisches Beispiel aus meinem Alltag – Daten als `struct`, Logik als Funktion, Speicherung in einem `vector`, statt einer eigenen `Spieler`-Klasse mit Methoden:
```cpp
struct Spieler {
    std::string name;
    int gesundheit;
};

void schaden_zufuegen(Spieler& s, int betrag) {
    s.gesundheit -= betrag;
}

bool ist_am_leben(const Spieler& s) {
    return s.gesundheit > 0;
}

int main() {
    std::vector<Spieler> gruppe = {{"Vincent", 100}, {"Alex", 80}};

    for (Spieler& s : gruppe) {
        schaden_zufuegen(s, 30);
    }

    for (const Spieler& s : gruppe) {
        std::cout << s.name << " lebt: " << ist_am_leben(s) << std::endl;
    }

    return 0;
}
```
Keine Klasse, keine Vererbung, kein `this` – nur Daten und Funktionen, die auf diesen Daten arbeiten. Das ist nicht nur performanter, sondern meistens auch leichter zu lesen und zu debuggen, weil du jederzeit genau weißt, wo deine Daten liegen und was mit ihnen passiert.

Wenn ihr euch also entscheidet, OOP-Konzepte wie Vererbung oder Polymorphismus zu lernen: Lernt sie richtig, versteht *wann* sie wirklich helfen – nicht nur, weil es "objektorientiert" heißt. Aber fangt nicht dort an. Fangt mit den wenigen, soliden Werkzeugen oben an. Die bringen euch in der Praxis am weitesten.

---

## Einstieg in meine Sprache (C<<)
**C<<** ("C-Shift", Dateiendung `.cll`) ist meine eigene, statisch typisierte und kompilierte Systemsprache. Sie folgt denselben Prinzipien, die im vorherigen Kapitel beschrieben wurden: kein versteckter Overhead, kein Garbage Collector, keine erzwungene OOP-Struktur. Der Unterschied zu C++: Vieles, was man dort manuell diszipliniert einhalten muss (RAII konsequent nutzen, keine wilden Pointer, klare Datenflüsse), erzwingt C<< direkt über den Compiler.

Ihr Paradigma nennt sich **VOP** (*Vertical Ownership Programming*): Speicher gehört immer genau einem Scope (einer "Arena"), und Daten fließen kontrolliert in eine Richtung durch dein Programm.

### Der Einstiegspunkt
Statt einer `main`-Funktion hat jedes C<<-Programm genau einen `entry`-Block:

```cll
import std;

entry
{
    puts("Hello, C<< world!");
}
```

`import std;` bindet die Standardbibliothek ein (vergleichbar mit `#include <iostream>` in C++). `puts()` gibt einen String aus, gefolgt von einem Zeilenumbruch.

---

### Variablen und Typen
Wie in C++ ist C<< statisch typisiert, allerdings sind die Zahlentypen explizit benannt – du siehst direkt, wie viele Bits ein Typ belegt:

| Typ | Bedeutung |
| :--- | :--- |
| `int8` / `int16` / `int32` / `int64` | Vorzeichenbehaftete Ganzzahlen (8/16/32/64 Bit) |
| `uint8` / `uint16` / `uint32` / `uint64` | Vorzeichenlose Ganzzahlen |
| `float32` / `float64` | Dezimalzahlen (entspricht `float`/`double` in C++) |
| `bool` | Wahrheitswert (`true`/`false`) |
| `char` | Einzelnes Byte |
| `string` | Text (im Hintergrund ein C-kompatibler `char*`) |
| `voided` | Entspricht `void` in C/C++ |

```cll
int32 x = 42;
float32 pi = 3.14159;
string name = "Alice";
const int32 MAX = 1024; // Konstanten mit "const", wie in C++
```

Mischst du Zahlentypen in einer Rechnung, wandelt der Compiler automatisch um ("Coercion") – bei einer möglichen Genauigkeits- oder Wertebereichs-Einbuße (z. B. `int64` → `int32`) bekommst du dafür eine Warnung vom Checker, bei unvereinbaren Typen einen harten Fehler.

---

### Funktionen und Tunnel
Hier unterscheidet sich C<< am deutlichsten von praktisch jeder anderen Sprache, die du bisher kennengelernt hast: Funktionen haben **keinen Rückgabetyp** und kein `return`. Stattdessen verlassen Werte eine Funktion über sogenannte **Tunnel**:

```cll
def add(int32 a, int32 b)
{
    tunnel a + b -> int32 result;
}
```

Beim Aufruf musst du vorher Platz "reservieren", in den der Tunnel seinen Wert hineinlegt:
```cll
entry
{
    reserve int32 result = add(3, 4);
    printf("%d\n", result); // 7
}
```
Man kann es sich wie eine Rohrpost vorstellen: `tunnel` schickt den Wert ab, `reserve` stellt den Briefkasten bereit, in dem er ankommt. Bei nur einem Tunnel-Ausgang kannst du eine Funktion auch ganz normal wie einen Ausdruck verwenden, ohne vorher zu reservieren:
```cll
printf("%d\n", add(4, 8)); // 12
```

Der Vorteil zeigt sich bei **mehreren Rückgabewerten** – etwas, das in C++ nur über Pointer/Referenzen oder ein eigenes struct umständlich lösbar ist:
```cll
def divide(int32 a, int32 b)
{
    tunnel a / b -> int32 quotient;
    tunnel a % b -> int32 remainder;
}

entry
{
    reserve int32 quotient;
    reserve int32 remainder;
    divide(17, 5);
    printf("%d r %d\n", quotient, remainder); // 3 r 2
}
```

Hat eine Funktion mehrere Tunnel-Ausgänge und du willst gezielt einen davon abgreifen, geht das explizit mit `<<`:
```cll
def compute(int32 x)
{
    tunnel x * 2 -> int32 doubled;
    tunnel x * 3 -> int32 tripled;
}

entry
{
    reserve int32 t << tripled = compute(10);
    printf("tripled = %d\n", t); // 30
}
```

**Forward Declarations (`dec`):** Rufen sich zwei Funktionen gegenseitig auf (Mutual Recursion), muss eine davon vorher mit `dec` angekündigt werden – ähnlich einer Funktionsdeklaration in C/C++:
```cll
dec is_odd(int32 n) -> int32 result;

def is_even(int32 n)
{
    if (n == 0) {
        tunnel 1 -> int32 result;
    } else {
        reserve int32 r = is_odd(n - 1);
        tunnel r -> int32 result;
    }
}

def is_odd(int32 n)
{
    if (n == 0) {
        tunnel 0 -> int32 result;
    } else {
        reserve int32 r = is_even(n - 1);
        tunnel r -> int32 result;
    }
}
```

---

### Kontrollfluss
`if`/`else`, `while`, `switch` und `break`/`continue` funktionieren wie in C++. Neu ist `foreach`, um direkt über ein Array zu iterieren:

```cll
if (x > 0) {
    puts("positiv");
} else if (x < 0) {
    puts("negativ");
} else {
    puts("null");
}

while (i < 10) {
    i += 1;
}

foreach (int32 val : arr) {
    printf("%d\n", val);
}

switch (status) {
    case 0:
        puts("ok");
    case 1:
        puts("error");
    default:
        puts("unbekannt");
}
```
Ein Detail, das DOD-Fans freuen dürfte: Ist eine `if`-Bedingung bereits zur Compile-Zeit bekannt (z. B. `1 == 1`), entfernt der Compiler den toten Zweig komplett aus dem erzeugten Code – ganz ohne Laufzeitkosten.

---

### Das Arena-Modell (Speicherverwaltung)
Erinnerst du dich an den Abschnitt [Speicherverwaltung](#speicherverwaltung) aus Kapitel 3? Dort ging es um GC, manuelle Verwaltung und automatische Freigabe am Scope-Ende. C<< entscheidet sich konsequent für Letzteres – und macht daraus sein zentrales Sprachfeature: das **Arena-Modell**.

Jeder `{ … }`-Block ist eine **Arena**. Alle Heap-Allokationen in diesem Block – dynamische Arrays, `Vector<T>`, `HashMap<K,V>` und so weiter – werden automatisch von dieser Arena verfolgt. Verlässt du den Block, gibt **ein einziger** interner Aufruf den kompletten Speicher dieses Blocks frei. Es gibt keine einzelnen Destruktoren wie in C++:

```cll
{
    Vector<int32> tmp = vec_new(8);
    tmp.push(42);
    // tmp wird hier automatisch komplett freigegeben
}
// Der äußere Scope ist davon nicht betroffen
```

Willst du Speicher freigeben, ohne den Scope zu verlassen, nutzt du `reset`:
```cll
int32[] buf;
buf << 1;
buf << 2;
reset;      // Speicher von buf wird freigegeben, Länge ist wieder 0
buf << 99;  // buf kann direkt weiterverwendet werden
```

Das Ergebnis: Du bekommst die Sicherheit eines Garbage Collectors (kein manuelles `free`, keine vergessenen Allokationen), aber ohne dessen Laufzeitkosten – die Freigabe passiert exakt vorhersehbar an Scope-Grenzen, nicht irgendwann im Hintergrund.

---

### Der "Voided State" und `move`
Damit du nie aus Versehen einen Wert benutzt, dessen Speicher bereits "woanders hingehört", kennt C<< für jede Variable zwei Zustände: **valid** und **voided**.

```cll
int32 x = 42;
move x;          // x ist jetzt voided
printf("%d", x); // [FEHLER] Use of voided variable 'x'
```

Willst du beide Fälle behandeln, nutzt du `switch` als Guard:
```cll
switch (x)
{
    case valid:
        printf("x = %d\n", x);
    case voided:
        puts("x wurde verschoben");
}
```
Das Besondere: Weiß der Compiler zur Compile-Zeit bereits sicher, dass `x` an dieser Stelle garantiert (oder garantiert nicht) voided ist, erzeugt er nur den jeweils zutreffenden Zweig – **zur Laufzeit kostet dich diese Sicherheit dann nichts**. Nur wenn es wirklich von einer Bedingung abhängt (z. B. `move` innerhalb eines `if`), erzeugt der Compiler ein verstecktes Flag, das zur Laufzeit geprüft wird.

---

### Arrays und Container
C<< unterscheidet drei Array-Arten:

```cll
int32[] nums;      // Arena-verwaltet, wächst dynamisch
nums << 10;        // Anhängen
nums << 20;
int32 x = nums[0]; // Lesen
nums[0] = 99;       // Schreiben
uint64 len = nums.len(); // Länge

float32[16] matrix; // Feste Größe, liegt auf dem Stack (wie float32 matrix[16] in C/C++)

int32[:] view;       // Non-owning Slice: Zeiger + Länge, besitzt den Speicher nicht
```

Für mehr Komfort gibt es generische Container, die – genau wie `std::vector` & Co. in C++ – arena-verwaltet sind und sich nie manuell freigeben lassen müssen:

```cll
Vector<int32> v = vec_new(16);
v.push(10);
v.push(20);
printf("len=%llu erstes=%d\n", v.len(), v.get(0));

HashMap<string, int32> scores = map_new();
scores.set("alice", 100);
int32 out = 0;
scores.get("alice", &out); // out = 100

StringBuilder sb = sb_new();
sb.append("Hello, ");
sb.append_int(42);
string ergebnis = sb.build();
```
Daneben gibt es noch `SortedVec<T>`, `LinkedList<T>`, `Set<T>`, `BitSet` und `Deque<T>` – alle nach demselben Methoden-Schema (`.push()`, `.get()`, `.len()`, …).

---

### Structs, Enums und Zero-Cost Classes
Ein `struct` ist reine Daten, genau wie in C++ – ohne Methoden:
```cll
struct Vec2
{
    float32 x;
    float32 y;
}

Vec2 p;
p.x = 3.0;
p.y = 4.0;
```

`enum` funktioniert wie erwartet, optional mit explizitem Basistyp:
```cll
enum Direction { North, South, East, West }
enum ErrorCode : int32 { Ok = 0, NotFound = 404 }
```

Spannend wird es bei `class`: Anders als in C++ gibt es hier **keine** Vererbung, keine virtuellen Methoden, keine Konstruktoren/Destruktoren – `class` ist reiner **Zucker** für genau das Muster, das ich dir im C++-Kapitel als "meinen Stil" empfohlen habe: ein `struct` plus freie Funktionen, die einen Pointer auf dieses struct als ersten Parameter (`self`) bekommen.

```cll
class Player
{
    float32 x;
    float32 y;
    int32 health;

    def take_damage(int32 amount)
    {
        self.health -= amount;
    }

    def is_alive() -> int32 alive
    {
        if (self.health > 0) {
            tunnel 1 -> int32 alive;
        } else {
            tunnel 0 -> int32 alive;
        }
    }
}

entry
{
    Player p;
    p.x = 0.0; p.y = 0.0; p.health = 100;

    p.take_damage(30);
    reserve int32 alive = p.is_alive();
    printf("health=%d alive=%d\n", p.health, alive); // health=70 alive=1
}
```
`p.take_damage(30)` übersetzt der Compiler 1:1 zu `Player_take_damage(&p, 30)` – ohne vtable, ohne Laufzeit-Overhead. Genau das DOD-Prinzip aus dem letzten Kapitel, nur direkt in der Sprache eingebaut: Du bekommst die bequeme `objekt.methode()`-Syntax, ohne die Nachteile "echter" OOP-Klassen zu erkaufen.

---

### Imports und C-Interop
C<< ist von Grund auf C-ABI-kompatibel, das heißt: Du kannst praktisch jede C-Bibliothek direkt einbinden.

```cll
import std;                  // C<<-Standardbibliothek
import "raylib.h";           // C-Header einbinden (über libclang)
import <stdio.h>;

import int32 printf(string fmt, ...); // Einzelne C-Funktion importieren
```
Das ist derselbe Mechanismus, über den z. B. die [Raylib](https://www.raylib.com/)-Integration funktioniert – Spiele-Fenster, Zeichenfunktionen und benannte Farbkonstanten (`RED`, `RAYWHITE`, …) lassen sich direkt aus C<< heraus nutzen, ganz ohne Wrapper-Code:

```cll
import "raylib.h";

entry
{
    InitWindow(800, 450, "Mein Spiel");
    SetTargetFPS(60);

    while (WindowShouldClose() == false)
    {
        BeginDrawing();
        ClearBackground(RAYWHITE);
        DrawText("Hello World!", 190, 200, 20, DARKGRAY);
        DrawCircle(400, 225, 50, RED);
        EndDrawing();
    }

    CloseWindow();
}
```

---

### Die Standardbibliothek (`std`)
`import std;` bringt unter anderem mit:

| Bereich | Beispiele |
| :--- | :--- |
| I/O | `printf()`, `puts()`, `scanf()`, `read_line_a()` |
| Sichere Strings | `str_len()`, `str_eq()`, `str_concat_a()`, `str_to_upper_a()`, `str_to_int()` |
| Datei-IO | `read_file_s_a()`, `write_file_s()`, `file_exists()`, `file_size_s()` |
| Mathematik | `sin()`, `sqrt()`, `pow()`, `abs()`, `rand()` |

Funktionen mit dem Suffix `_a` (für "arena") geben einen Wert zurück, der automatisch von der aktuellen Arena verwaltet wird – du musst dich auch hier um nichts manuell kümmern:

```cll
string s = "Hello, World!";
printf("len=%d\n", str_len(s));
printf("upper=%s\n", str_to_upper_a(s, __arena));

int32 ok = write_file_s("/tmp/test.txt", "hallo von C<<\n");
if (ok == 0) {
    string content = read_file_s_a("/tmp/test.txt", __arena);
    printf("gelesen: %s", content);
}
```

---

### Ein vollständiges Beispiel
Zum Abschluss ein etwas größeres Beispiel, das mehrere der gezeigten Konzepte kombiniert – Fibonacci-Zahlen, berechnet über eine Tunnel-Funktion:

```cll
import std;

def fib(int32 n)
{
    int32 a = 0;
    int32 b = 1;
    int32 i = 0;
    while (i < n)
    {
        int32 tmp = b;
        b = a + b;
        a = tmp;
        i += 1;
    }
    tunnel a -> int32 result;
}

entry
{
    int32 i = 0;
    while (i < 10)
    {
        reserve int32 r = fib(i);
        printf("fib(%d) = %d\n", i, r);
        i += 1;
    }
}
```

---

### Der Weg zu 1.0: Self-Hosting
C<< befindet sich aktuell auf dem Weg zum 0.9-Release – die Sprachsemantik (Tunnel, Arena-Modell, Voided State, Generics, …) steht bereits. Bis 1.0 fehlt bewusst noch ein letzter, großer Meilenstein: **Self-Hosting**.

Aktuell ist der C<<-Compiler selbst in C++ geschrieben – ein sogenannter **Bootstrap-Compiler**. Self-Hosting bedeutet, dass eine Sprache ihren eigenen Compiler kompilieren kann: Der C<<-Compiler muss also irgendwann selbst in C<< geschrieben sein.

Der Weg dahin läuft typischerweise so ab:
1. **Stage 0:** Der bestehende C++-Compiler bleibt zunächst unverändert bestehen und dient als Werkzeug.
2. **Stage 1:** Ich schreibe einen neuen C<<-Compiler – diesmal in C<< selbst – und übersetze ihn mit dem Stage-0-Compiler. Ergebnis: eine ausführbare Datei, die C<< versteht und selbst in C<< geschrieben ist.
3. **Stage 2:** Mit diesem frisch gebauten Stage-1-Compiler kompiliere ich denselben C<<-Quellcode noch einmal.
4. **Verifikation:** Verhalten sich die von Stage 1 und Stage 2 erzeugten Compiler identisch, gilt die Sprache als **selbsttragend (self-hosted)**. Ab dann ist der C++-Bootstrap-Compiler nur noch für den allerersten Schritt nötig – alles Weitere kann C<< mit sich selbst erledigen.

Dieser Schritt ist so ein wichtiger Meilenstein, weil er beweist, dass eine Sprache vollständig genug ist, um damit reale, komplexe Software zu schreiben – in diesem Fall sich selbst. Deshalb ist Self-Hosting für mich die Bedingung für 1.0, nicht nur ein "nice to have".

---

## Tools und Installation

### Das Terminal
Bevor wir uns Schritt für Schritt durch die Installation arbeiten, klären wir kurz: Was ist eigentlich ein **Terminal** (auch Konsole oder Kommandozeile genannt)?

Normalerweise bedienst du deinen Computer über eine grafische Oberfläche (GUI) – du klickst auf Symbole, öffnest Fenster, ziehst Dateien hin und her. Ein Terminal ist die "andere" Art, mit deinem Computer zu sprechen: Statt zu klicken, tippst du Befehle als Text ein, und der Computer führt sie aus.

Beispiel: Statt im Dateimanager in einen Ordner zu klicken, tippst du:
```bash
cd Dokumente   # cd = "change directory", wechselt in den Ordner "Dokumente"
ls             # Listet alle Dateien im aktuellen Ordner auf (unter Windows: dir)
```

Wieso nutzen Programmierer das Terminal so häufig, obwohl es auf den ersten Blick umständlicher wirkt?
* Viele Tools (Compiler, Skripte, Versionsverwaltung) haben gar keine grafische Oberfläche – das Terminal ist ihr einziger Zugang.
* Befehle lassen sich exakt wiederholen, automatisieren und in Skripten speichern.
* Auf entfernten Servern (z. B. beim Deployment) gibt es oft überhaupt keine grafische Oberfläche.

Den Begriff "Terminal" benutzt man meist plattformübergreifend. Unter Windows heißt die klassische Variante **Eingabeaufforderung (cmd)** oder moderner **PowerShell**, unter Mac und Linux schlicht **Terminal** bzw. **Shell**. Welche Shell du konkret nutzt (z. B. `bash`, `zsh`), spielt für den Einstieg erstmal keine Rolle – die Grundbefehle ähneln sich stark. In diesem Kapitel gehen wir von `bash` aus, der Standard-Shell unter Linux, Mac und WSL.

---

### Grundlegende Bash-Befehle
Eine kleine Übersicht der Befehle, die du ständig brauchen wirst:

| Befehl | Bedeutung |
| :--- | :--- |
| `pwd` | Zeigt den aktuellen Ordner an ("print working directory") |
| `cd <ordner>` | Wechselt in einen Ordner. `cd ..` geht eine Ebene hoch, `cd ~` geht ins Home-Verzeichnis |
| `ls` | Listet Dateien im aktuellen Ordner auf (`ls -la` zeigt auch versteckte Dateien + Details) |
| `mkdir <name>` | Erstellt einen neuen Ordner |
| `touch <datei>` | Erstellt eine leere Datei |
| `rm <datei>` | Löscht eine Datei (`rm -r <ordner>` löscht einen ganzen Ordner – landet **nicht** im Papierkorb!) |
| `cp <quelle> <ziel>` | Kopiert eine Datei (`cp -r` für ganze Ordner) |
| `mv <quelle> <ziel>` | Verschiebt eine Datei oder benennt sie um |
| `cat <datei>` | Gibt den Inhalt einer Datei direkt im Terminal aus |
| `clear` | Leert den Terminal-Bildschirm |
| `man <befehl>` | Öffnet das Handbuch zu einem Befehl (mit `q` wieder verlassen) |

Ein typischer Ablauf, um ein neues Projekt anzulegen:
```bash
mkdir mein_projekt
cd mein_projekt
touch main.cpp
code .   # Öffnet den Ordner in VS Code (siehe nächste Abschnitte)
```

---

### WSL (Windows Subsystem for Linux)
Ein Großteil der Tools, die wir im Folgenden nutzen – Compiler, Build-Systeme, der C<<-Compiler selbst – ist ursprünglich für Unix-artige Systeme (Linux, Mac) gebaut. Unter Windows lässt sich das zwar teilweise nativ nachbauen, ist aber meist umständlicher und fehleranfälliger.

Deswegen empfehle ich unter Windows ausdrücklich **WSL** (*Windows Subsystem for Linux*): Es gibt dir ein echtes Ubuntu-Linux direkt innerhalb von Windows, ganz ohne virtuelle Maschine oder Dual-Boot.

**Installation:**
1. Öffne die **PowerShell als Administrator** (Rechtsklick auf das Startmenü → "Terminal (Administrator)" bzw. "Windows PowerShell (Administrator)").
2. Führe folgenden Befehl aus:
```powershell
wsl --install
```
3. Starte deinen PC neu, wenn du dazu aufgefordert wirst.
4. Nach dem Neustart öffnet sich automatisch ein Ubuntu-Fenster. Vergib einen Benutzernamen und ein Passwort – das ist dein Linux-Nutzerkonto, unabhängig von deinem Windows-Login.

Ab jetzt kannst du dein Ubuntu-Terminal jederzeit öffnen, indem du im Startmenü `wsl` oder `Ubuntu` eingibst. Alle folgenden Schritte (Python, Compiler, C<<) führst du unter Windows **innerhalb von WSL** aus – also in diesem Ubuntu-Fenster, nicht in der normalen Windows-Eingabeaufforderung.

---

### VS Code installieren und mit WSL nutzen
**VS Code** (Visual Studio Code) ist ein kostenloser, leichtgewichtiger Code-Editor und für den Einstieg völlig ausreichend.

**Installation (Windows/Mac/Linux):**
1. Lade VS Code von [code.visualstudio.com](https://code.visualstudio.com/) herunter.
2. Installiere es wie jedes andere Programm (Installer ausführen, "Weiter" klicken).

**VS Code mit WSL verbinden (nur unter Windows relevant):**
Damit du Dateien bearbeiten kannst, die in deinem Linux-Dateisystem (WSL) liegen, brauchst du eine Verbindung zwischen VS Code (läuft als Windows-Programm) und WSL:

1. Öffne VS Code und installiere die Extension **"WSL"** (im Extensions-Tab links, Symbol mit den vier Quadraten, danach suchen).
2. Öffne dein Ubuntu-Terminal (WSL) und wechsle in den Ordner, in dem du arbeiten willst, z. B.:
```bash
mkdir projekte && cd projekte
```
3. Tippe dort:
```bash
code .
```
Das öffnet VS Code direkt aus WSL heraus, verbunden mit deinem Linux-Dateisystem. Du erkennst die aktive WSL-Verbindung unten links in VS Code an einem grünen Symbol mit der Aufschrift "WSL: Ubuntu".

Auf Mac und Linux brauchst du diesen Schritt nicht – dort arbeitest du ohnehin direkt im "echten" Dateisystem.

---

### Git und GitHub CLI (gh)
**Git** ist ein Versionsverwaltungssystem: Es speichert die komplette Historie deines Codes, sodass du jederzeit zu einem früheren Stand zurückkehren kannst und mehrere Leute am selben Projekt arbeiten können, ohne sich gegenseitig zu überschreiben.

Installation:
| Plattform | Befehl |
| :--- | :--- |
| WSL/Linux | `sudo apt install git` |
| Mac | `brew install git` (oder bereits über die Xcode Command Line Tools vorhanden) |
| Windows | [git-scm.com](https://git-scm.com/) (falls du nicht über WSL arbeitest) |

Die wichtigsten Befehle:
```bash
git clone <url>           # Ein Repository herunterladen
git status                # Was hat sich geändert?
git add <datei>           # Änderung zum nächsten Commit vormerken
git commit -m "Nachricht" # Änderungen dauerhaft speichern
git push                  # Eigene Commits hochladen
git pull                  # Neue Commits von anderen herunterladen
```

Die **GitHub CLI** (`gh`) ist ein Zusatztool, mit dem du GitHub (Repos, Pull Requests, Issues) direkt aus dem Terminal bedienst, ohne den Browser zu öffnen:
```bash
gh auth login                     # Einmalig mit deinem GitHub-Account verbinden
gh repo clone LuxUmbris/C-Shift   # Repo klonen
```
Installation: [cli.github.com](https://cli.github.com/) bzw. `sudo apt install gh` unter WSL/Linux, `brew install gh` unter Mac.

---

### SSH
**SSH** (*Secure Shell*) verschlüsselt eine Verbindung zwischen zwei Rechnern. Damit kannst du dich z. B. in einen entfernten Server einloggen oder dich gegenüber GitHub authentifizieren, ohne bei jedem `git push` ein Passwort einzugeben.

```bash
ssh nutzername@server-adresse   # Verbindung zu einem Server aufbauen
ssh-keygen -t ed25519           # Eigenes SSH-Schlüsselpaar erzeugen
```
Den dabei erzeugten **öffentlichen** Schlüssel (`~/.ssh/id_ed25519.pub`) kannst du z. B. bei GitHub unter "SSH and GPG keys" hinterlegen. Der **private** Schlüssel (ohne `.pub`) bleibt immer ausschließlich auf deinem Rechner und wird niemals geteilt.

---

### Archive: zip und xz
Zum Verpacken und Komprimieren von Dateien – etwa um sie zu verschicken oder Speicherplatz zu sparen – gibt es zwei gängige Werkzeuge.

**zip** ist weit verbreitet und auch unter Windows ohne Zusatztools entpackbar:
```bash
zip -r archiv.zip mein_ordner/   # Ordner packen
unzip archiv.zip                  # Entpacken
```

**xz** komprimiert meist deutlich stärker als zip, üblicherweise in Kombination mit `tar` (das Dateien erstmal nur bündelt, ohne sie zu komprimieren):
```bash
tar -cJf archiv.tar.xz mein_ordner/   # Packen + xz-komprimieren
tar -xJf archiv.tar.xz                # Entpacken
```

Installation, falls nicht bereits vorhanden: `sudo apt install zip unzip xz-utils` (WSL/Linux).

---

### Python installieren
| Plattform | Vorgehen |
| :--- | :--- |
| **Windows** | Installer von [python.org](https://www.python.org/downloads/) herunterladen. Wichtig: Beim Setup die Checkbox **"Add python.exe to PATH"** aktivieren. |
| **WSL** *(empfohlen unter Windows)* | `sudo apt update && sudo apt install python3 python3-pip` |
| **Mac** | Über [Homebrew](https://brew.sh/): `brew install python3` (Homebrew muss vorher installiert sein) |
| **Linux** | Meist bereits vorinstalliert. Sonst z. B. `sudo apt install python3 python3-pip` (Ubuntu/Debian) oder `sudo dnf install python3` (Fedora) |

Prüfen, ob die Installation funktioniert hat:
```bash
python3 --version
```

---

### C++ Compiler installieren (clang++ / g++)
Für C++ brauchst du einen Compiler. Die zwei gängigsten sind **g++** (GNU Compiler Collection) und **clang++** (LLVM-basiert) – für den Einstieg ist es egal, welchen du nimmst.

| Plattform | Vorgehen |
| :--- | :--- |
| **WSL / Linux** *(Ubuntu/Debian)* | `sudo apt update && sudo apt install build-essential` installiert g++. Für clang++: `sudo apt install clang` |
| **Mac** | `xcode-select --install` installiert die Xcode Command Line Tools, inklusive clang++ |
| **Windows** *(nativ, nicht empfohlen)* | Über [LLVM](https://releases.llvm.org/) (clang++) oder [MSYS2](https://www.msys2.org/) (g++). Erspar dir das nach Möglichkeit und nutze stattdessen WSL. |

Prüfen, ob die Installation funktioniert hat:
```bash
g++ --version
# oder
clang++ --version
```

---

### gdb – der Debugger
**gdb** (*GNU Debugger*) lässt dich ein C/C++-Programm Schritt für Schritt durchgehen, Variablenwerte zur Laufzeit ansehen und Abstürze (z. B. Segfaults) genau lokalisieren – deutlich präziser, als nur `printf`-Aufrufe in den Code zu streuen.

Installation: `sudo apt install gdb` (WSL/Linux). Unter Mac ist `lldb` die gängigere Alternative (über die Xcode Command Line Tools bereits enthalten) und funktioniert sehr ähnlich.

Damit gdb sinnvolle Informationen anzeigen kann, kompilierst du mit Debug-Symbolen (`-g`):
```bash
g++ -g programm.cpp -o programm
gdb ./programm
```

Die wichtigsten gdb-Befehle:
```
run          # Programm starten
break main   # Haltepunkt (Breakpoint), z. B. an main, setzen
next         # Nächste Zeile ausführen (springt NICHT in Funktionsaufrufe hinein)
step         # Nächste Zeile ausführen (springt in Funktionsaufrufe hinein)
print x      # Aktuellen Wert der Variable x anzeigen
continue     # Bis zum nächsten Breakpoint weiterlaufen
quit         # gdb verlassen
```

---

### Den C<< Compiler (cshift) installieren
Das Repository klonst du am einfachsten über die GitHub CLI:
```bash
gh repo clone LuxUmbris/C-Shift
cd C-Shift
```

Alternativ funktioniert das auch ganz klassisch mit Git:
```bash
git clone https://github.com/LuxUmbris/C-Shift.git
cd C-Shift
```

Der Compiler sowie die Runtime werden über **CMake** gebaut. Du brauchst dafür zusätzlich `cmake` (z. B. via `sudo apt install cmake` unter WSL/Linux oder `brew install cmake` unter Mac) sowie den C++-Compiler aus dem vorherigen Abschnitt.

> **Hinweis:** Der genaue Build-Ablauf (Skripte, Targets) befindet sich noch in Bewegung, da C<< aktuell auf das 0.9-Release zuarbeitet. Die jeweils aktuellen, exakten Schritte findest du im README des Repositories.

Für Syntax-Highlighting und weitere Sprachfeatures in VS Code gibt es außerdem eine offizielle C<<-Extension – im Marketplace einfach nach `cshift` suchen.

---

###### Copyright (c) 2026 LuxUmbris (GitHub)
