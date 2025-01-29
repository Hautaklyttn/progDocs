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

## Integer und Float

### *float* auf Nachkommastellen runden
```python
inputNumber = 4.56782
print("Rounding 4.56782 upto 2 decimal places:", format(inputNumber,".2f"))
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

### Substring in String:
```python
if "substring" in someString:
  # do something
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

