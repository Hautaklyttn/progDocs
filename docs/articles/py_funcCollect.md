---
layout: default
---

{::options parse_block_html="true" /}  

[Back](../)  

&nbsp;

# Function Collection: Python
---  

&nbsp;

## Conversion functions  

### string-to-binary

```python
binBitmuster = bin(int(strBitmuster,2))
```

### hex-to-decimal

```python
dec = int(hexWert, 16)
```

### hex-to-binary

```python
bin = bin(int(hexWert, 16))
```

### binary-to-hex

```python
hex = hex(int(binString, 2))
```

### Cast to boolean

```python
def str2bool(v):
  return str(v).lower() in ("yes", "true", "t", "1")
```

---

&nbsp;

## Bit operation functions

### setBit

```python
def setBit(bitString:int, bit:int):
    return (bitString | (1<<bit))
```

### getBit

```python
def getBit(bitString:int, bit:int):
    return (bitString >> bit) & 1
```

### clearBit

```python
def clearBit(bitString:int, bit:int):
    return (bitString & ~(1<<bit))
```

### bit position in string zurückgeben

```python
def Log2n(n:int):
	if (n > 1):
		return (1 + self.Log2n(n / 2))
	else:
		return 0
```

---

&nbsp;

## Objektorientierung

### Check ob zwei Instanzen von Klasse identisch
```python
# id(object) returns a unique number (identity) that adapts the philosophy of C-style pointer
x is y 
# oder
id(x) == id(y)
```

---

&nbsp;

## Integer und Float

### *float* auf Nachkommastellen runden
```python
inputNumber = 4.56782
print("Rounding 4.56782 upto 2 decimal places:", format(inputNumber,".2f"))
```

### *int* auf 100, 1000, usw. runden
```python
var = 560
rounded = round(var, -2)
# output: 600
var = 5400
rounded = round(var, -3)
# output: 5000
```

---

&nbsp;

## String

### Substring extrahieren
```python
s = 'gfgfdAAA1234ZZZuijjk'
start = s.find('AAA') + 3
end = s.find('ZZZ', start)
print(s[start:end])
   >> '1234'
```

### Substring in String
```python
if "substring" in someString:
  # do something
```

### String mit Kommas in Liste umwandeln
```python
my_string = 'A,B,C,D,E'
my_list = my_string.split(",")
```

---

&nbsp;

## Listen 

### Mehrere Listen auf Länge testen

```python
length = len(list1)
if all(len(lst) == length for lst in [list2, list3, list4, list5, list6]):
  # alle Listen gleich lang
if any(len(lst) != length for lst in [list2, list3, list4, list5, list6]):
  # eine Liste anderer Länge
```

### Mehrere Listen leeren

```python
list1, list2, list3 = [], [], []
```

### Initialisierung list-of-lists

```python
# To make a list of 3 different lists, do this:
x = [[] for i in range(3)]
```

### Durch Liste iterieren und Elemente löschen

```python
for i in range(len(somelist) - 1, -1, -1):
  if some_condition(somelist, i):
    del somelist[i]
```

### Check ob alle Elemente in Liste gleich

```python
if mylist.count(mylist[0]) == len(mylist):
  # do something
```

### Mehrere Elemente an Liste anhängen

```python
list.extend([elem1, elem2, ...])
```

### Liste in for-loop an bestimmtem Index beginnen

```python
for item in some_list[1:]:
  # do something
```

### Datentyp für alle Elemente einer Liste umwandeln

```python
results = ['1', '2', '3']
# Use 'map' then 'list' to obtain a list of integers:
list(map(int, results))
```

### Maximaler/Minimaler Wert aus Liste

```python
maxWert = max(<liste>)
minWert = min(<liste>)
```

### Werte in Liste Variablen zuweisen

```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
```

### Neue Liste mit jedem x-ten Element aus alter Liste

```python
xs = list(range(165))
xs[0::10]
# Output: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120, 130, 140, 150, 160]
```

### Liste von 0 bis n-1 mit ansteigenden Werten

```python
list(range(0, n))
```

### Liste von Nullen erstellen

```python
listofzeros = [0] * n
```

### Alle Listenelemente die Substring enthalten zurückgeben

```python
xs = ['abc-123', 'def-456', 'ghi-789', 'abc-456']
matching = [s for s in xs if "abc" in s]
```

### String in Substring in Liste finden

```python
xs = ['abc-123', 'def-456', 'ghi-789', 'abc-456']
if any("abc" in s for s in xs):
	...
```

### Liste in String umwandeln

```python
_list = [1,2,3]
_str = ''.join(str(i) for i in _list)
# output: '123'
```

---

&nbsp;

## Dictionaries (dict, defaultdict)

### *defaultdict()*

**Key**  
Key muss immer ein immutable Datentyp sein, d.h. strings oder integer/float.  

**Value**  

|Ziel   |Code   |
|:---|:---|
|Ein dictionary mit 'value' = Liste   |```d = defaultdict(list)```   |
|Ein dictionary mit 'value' = String   |```d = defaultdict(str)```   |
|Ein nested dictionary mit 'value' = integer   |```d = defaultdict(lambda: defaultdict(int))```   |  

Beispiel:
```python
d["one"][1] = 123

# Wert auslesen
d.get('one', {}).get(1)
```

---

&nbsp;

## File und Pfad 

### Pfad ohne Filenamen
```python
os.path.dirname(full_path)
```

### Filenamen von Pfad
```python
os.path.basename(full_path)
```

### Ermitteln der Anzahl der Zeilen in File
```python
num_lines = sum(1 for _ in open('myfile.txt'))
```

### Ordner erstellen (und vorher prüfen)
```python
if not os.path.isdir(<path>):
  os.makedirs(<path>)
```

### Alle Files in Ordner zurückgeben
```python
import os
all_files = [f for f in Path(<pfad>).iterdir() if f.is_file()]
```

### Check ob File existiert
```python
import os
os.path.isfile(fname)
```

### File-Größe ermitteln
```python
import os
os.path.getsize("/path/to/file")
# Output in bytes: 2071611
```

### Erstellungs/Modifikations-Datum für Files
```python
# 'Creation' time
os.path.getctime(path_to_file)

# 'Modification' time
os.stat(path_to_file)
```

---

&nbsp;

## Virtual Environment (*venv*) 

| Ziel  |Befehl Kommandozeile|
|:---|:---|
|Einrichten einer venv in aktuellem Verzeichnis:   |```python -m venv .venv```    |
|Einrichten einer venv mit spezieller Python-Version:   |```"C:\Program Files\Python313\python.exe" -m venv .venv```   |
|Ermitteln welcher Interpreter gerade aktiv im Verzeichnis:   |```where python```     |
|Ermitteln welche Module aktuell installiert sind in aktueller venv:   |```pip list```   |
|Aktivieren der virtuellen Umgebung im aktuellen Pfad:   |```<venv>/Scripts/activate.bat ausführen```   |
|Installieren von Modulen in File:   |```pip install -r requirements.txt```   |

---

&nbsp;

## Multiprocessing

### Ausgabe der aktuellen 'worker' process id
```python
print(multiprocessing.current_process())
```

### Dauer der Codeabarbeitung über alle Subprozesse hinweg loggen
```python
import time

start = time.time()

# ... Aufruf der Subprozesse ...

print(time.time() - start) 
```

---

&nbsp;

## tkinter  

### Widgets referenzieren (auch untergeordnete)
```python
# You can give widgets names when you create them
note = Notebook(root, name="George")
tab2 = Frame(note, name="Tabby")

# And find widgets by name using nametowidget
tab2 = root.nametowidget("George.Tabby")
```

### Frame Breite dynamisch ändern
```python
frame.config(width=100)
```

### Widgets visuell nach vorne bringen
```python
widget.lift()
```

---

&nbsp;

## print-Ausgabe, Debugging  

### print-Ausgabe ohne newline am Ende
```python
print("some string", end="", flush=True)
```

### print-Ausgabe in Farbe
```python
import os
os.system("")

# Class of different styles
class style():
   BLACK = '\033[30m'
   RED = '\033[31m'
   GREEN = '\033[32m'
   YELLOW = '\033[33m'
   BLUE = '\033[34m'
   MAGENTA = '\033[35m'
   CYAN = '\033[36m'
   WHITE = '\033[37m'
   UNDERLINE = '\033[4m'
   RESET = '\033[0m'
   
print(f"{style.GREEN} some_text ")
```

### Auf Konsole ausgeben obwohl stdout umgeleitet auf File/Widget
```python
print("start_TriggerErroreingang gestartet...", file=sys.__stdout__, flush=True)
```

---

&nbsp;

## Misc functions  

### Quersumme bilden

```python
bitPos = 000100
sum([int(i) for i in str(bitPos)])
```

### One line if-else

Syntax: [statement1 if expression1 else statement2]

```python
x = 2 if y == 0 else 1
```
**Aber:** Nicht immer möglich! Funktioniert z.B. nicht für: ```n+=1 if exp > 2 else 0```

### Abbrechen von while-loop durch Tastendruck

```python
try:
  while True:
    # do something
except KeyboardInterrupt:
  pass
```

### Optionale Argumente an Funktion

```python
def example_function(param1, param2, param3=None, param4=None):
  pass

# Doesn't work, param2 missing
example_function("hello")

# Works
example_function("hello", "bye")

# Works. Both the same
example_function("hello", "bye", "hey")
example_function("hello", "bye", param3="hey")

# Works. Both the same
example_function("hello", "bye", "hey", "foo")
example_function("hello", "bye", param3="hey", param4="foo")
```

### Mehrere Werte mehreren Variablen zuweisen
```python	
x, y, z = "Orange", "Banana", "Cherry"
```

### Ein Wert mehreren Variablen zuweisen
```python	
x = x = z = "Orange"
```

### 'NUL' character erfassen
```python	
if '\x00' in someString:
  # do something
```

### 'Moving Average'
```python	
new_average = (old_average * (n-1) + newVal) / n
```

### Auf leere Zeile prüfen
```python	
if len(line.strip()) == 0:
  # do sth
```

### Dynamisch Variablen ansprechen
```python	
c = {"one": 1, "two": 2}
for k, v in c.items():
  exec(f"{k} = {v}")
```




