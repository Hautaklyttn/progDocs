---
layout: default
---

[Back](../)

&nbsp;

# Python
---

&nbsp;

### 1. Basics    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 Geschichte</font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 Allgemeines</font>](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2.1 Der Interpreter, eine interaktive Shell</font>](#ch1-2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2.2 Problem: 'Lack of Compile time checks'</font>](#ch1-2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3 Python Virtual Machine (PVM)</font>](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.4 Variablen in Python</font>](#ch1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.5 Strings</font>](#ch1-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.6 Aufruf eines Python-Skripts (*.py)</font>](#ch1-6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.7 Decorators</font>](#ch1-7)  

### 2. Functions
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Basic Functions</font>](#ch2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1.1 Funktion id()</font>](#ch2-1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1.2 Funktion dir()</font>](#ch2-1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1.3 Funktion help()</font>](#ch2-1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1.4 Funktion type()</font>](#ch2-1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.2 String Functions</font>](#ch2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3 OO related Functions</font>](#ch2-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3.1 Funktion issubclass()</font>](#ch2-3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3.2 Funktion isinstance()</font>](#ch2-3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3.3 Funktion super()</font>](#ch2-3-3)  

### 3. Listen
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 Basics</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 List Functions</font>](#ch3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.3 ...</font>](#ch3-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.4 ...</font>](#ch3-4)  

### 4. Dictionaries   

### 5. HowTo's
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.1 File handling</font>](#ch5-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.2 Regular Expressions</font>](#ch5-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.2.1 Basics</font>](#ch5-2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.2.2 Syntax regulärer Ausdrücke</font>](#ch5-2-2)  

&nbsp;

---  

# Basics

&nbsp;

<a name="ch1-1"></a>
### 1.1 Geschichte  
Die Sprache wurde Anfang der 1990er Jahre von Guido van Rossum am Zentrum für Mathematik (Centrum voor Wiskunde en Informatica) in Amsterdam entwickelt. Ursprünglich war sie als Nachfolger für die Lehrsprache ABC entwickelt worden und sollte auf dem verteilten Betriebssystem Amoeba laufen. Guido van Rossum hatte auch an der Entwicklung der Sprache ABC mitgewirkt, so dass seine Erfahrungen mit ABC auch in Python einflossen.  

&nbsp;

<a name="ch1-2"></a>
### 1.2 Allgemeines  

<a name="ch1-2-1"></a>
#### 1.2.1 Der Interpreter, eine interaktive Shell  
Im Englischen steht das Wort "shell" für eine Schale, einen Panzer oder ganz allgemein eine Hülle oder Schutzhülle. "Shell" bezeichnet auch ein Schneckenhaus und das Gehäuse, das eine Muschel umschließt. Ebenso liegt eine Shell auch zwischen einem Betriebssystem und dem Benutzer. Wie eine Muschelschale schützt sie zum einen das Betriebssystem vor dem Benutzer und gleichzeitig erspart sie dem Benutzer die Benutzung der "primitiven" und schwer verständlichen Basisfunktionen, indem sie ihm komfortable Befehle zur Kommunikation mit dem Computer zur Verfügung stellt.  

Auch die Programmiersprache Python bietet dem Anwender eine komfortable Kommandozeilen-Schnittstelle, die sogenannte Python-Shell, die man manchmal auch als interaktive Python-Shell bezeichnet. Man könnte meinen, dass es sich bei dem Begriff "interaktive Shell" um eine Tautologie handelt, da ja, so wie wir es oben beschrieben haben, Shells immer interaktiv sind. Dies ist jedoch nicht so: Es gibt auch vor allem im Umfeld von Linux und Unix Shells, die als Subshell aufgerufen werden und nicht interaktiv ausgeführt werden.  

Man kann Python im interaktiven Modus aufrufen, indem man den Interpreter in einer Linux-Shell (Bash-Shell) ohne Parameter aufruft. Also  
```js
>>> python
```

&nbsp;

Weitere Möglichkeit der interaktiven Arbeit ist der Online-Interpreter:  
[&rarr; &nbsp; Link](http://www.python-online.ch/pyonline/PyOnline.php)  

&nbsp;

<a name="ch1-2-2"></a>
#### 1.2.2 Problem: 'Lack of Compile time checks'  
As Python code is not generally compiled prior to execution, there is no general mechanism in place to check the code for certain types of errors before executing the program. <u>This means that errors will only be detectable during runtime, requiring sophisticated and extensive testing strategies before publishing code.</u> However, it may well be impossible to test every single path through the code under all circumstances, in particular if user input is involved, potentially leaving an arbitrary number of undetected errors in the code. While this is true to some degree for compiled languages as well, a significant number of errors would already be detected at compile time, while all errors in Python code exclusively occur during runtime.

&nbsp;

<a name="ch1-3"></a>
### 1.3 Python Virtual Machine (PVM)  
Ruft man das Skript in der Kommandozeile direkt auf, dann wird das Skript in Bytecode übersetzt und ausgeführt. Diesen Byte-Code bekommt die Anwenderin oder der Anwender nicht zu Gesicht.

Das ändert sich, wenn man in einem anderen Python-Skript oder auch in der Python-Shell dieses Skript mittels dem Kommando "import" importiert. In diesem Fall wird eine in Bytecode übersetzte Version des Python-Programmes abgespeichert. Diese ist nicht mehr so einfach zu finden, wie dies in Python2 der Fall war. Die Datei befindet sich nun in einem Unterverzeichnis ``__pycache__``.

![001](../assets/pics/byte_code.png)   

Bei einem späteren "import" in einem anderen Programmlauf, wird dann direkt die Datei mit dem Byte-Code geladen. Importiert man die gleiche Datei mehrmals im gleichen Skript wird sie nur beim ersten Mal geladen.  

Bei dem Byte-Code handelt es sich um einen maschinenunabhängigen Code, der mittels einer virtuellen Maschine (PVM, ``Python Virtual Machine``) ausgeführt wird.

&nbsp;

<a name="ch1-4"></a>
### 1.4 Variablen in Python  
Es gibt gravierende Unterschiede in der Art wie Python und C bzw. C++ Variablen behandeln. Vertraute Datentypen wie Ganzzahlen (Integer), Fließkommazahlen (floating point numbers) und Strings sind zwar in Python vorhanden, aber auch hier gibt es wesentliche Unterschiede zu C und C++.

In Programmiersprachen wie C, C++ oder Java hat jede Variable einen eindeutigen Datentyp. Das bedeutet, dass falls beispielsweise eine Variable vom Typ Integer ist, sie nur Integer-Werte aufnehmen kann. In diesen Programmiersprachen müssen Variablen auch vor ihrer Benutzung deklariert werden. Deklaration bedeutet Bindung an einen Datentyp, der dann für den gesamten Programmablauf unveränderlich ist.  

In Python haben wir eine gänzlich andere Situation. Zunächst einmal bezeichnen Variablen in Python keinen bestimmten Typ und deshalb benötigt man auch in Python keine Typdeklaration. Benötigt man im Programm beispielsweise eine Variable i mit dem Wert 42, so erreicht man dies einfach mit der folgenden Anweisung:  
```
>>> i = 42
```

In Python kann zur Laufzeit sowohl der Wert einer Variablen geändert werden, als auch der Typ einer Variablen. Präziser: Ein neues Objekt eines beliebigen Typs wird der Variablen zugewiesen. Wir verdeutlichen dies in folgendem Beispiel:  
```
i = 42        # Typ wird implizit auf Integer gesetzt
i = 41 + 0.11	# Typ wird in float geändert
i = "fünfzig"	# Jetzt ist es ein string

```

&nbsp;

>  Variablen referenzieren Objekte in Python. Die eigentlichen Daten sind jedoch im Objekt enthalten.

&nbsp;

```
>>> x = 42  # Variable x zeigt auf ein Int-Objekt
>>> y = x   # Eine zweite Variable referenziert jetzt das gleiche Objekt wie x
```

Was wird passieren, wenn wir nun die Zuweisung y = 78 ausführen?  
**Python wird zuerst ein neues Integer-Objekt mit dem Inhalt '78' erzeugen und dann wird die Referenz von y auf dieses Objekt geändert. Wichtig ist dabei, dass x nach wie vor das alte Objekt referenziert, d.h. der Wert ist nach wie vor '42'.**  
(&rarr; s. Kapitel 2.1: Funktion id() zum Prüfen der Identität)

Wird x jetzt ein String zugewiesen, wäre das Integer-Objekt '42' verwaist. Es muss von Python entfernt werden, da es von keiner anderen Variable referenziert wird.

&nbsp;

<a name="ch1-5"></a>
### 1.5 Strings  
Ein String, oder Zeichenkette, kann man als eine Sequenz von einzelnen Zeichen sehen.
Jedes einzelne Zeichen eines Strings, kann über einen Index angesprochen werden:  

```
>>> s = "Python"
>>> print(s[0])
P
>>> print(s[3])
h
```

&nbsp;  

**Achtung:**
> Wie in Java aber nicht wie in C oder C++, können Strings in Python nicht verändert werden. Versucht man eine indizierte Position zu ändern, erzeugt man eine Fehlermeldung.

&nbsp;

<a name="ch1-6"></a>
### 1.6 Aufruf eines Python-Skripts (\*.py)

Von der cmd shell  
```
python someFile.py
```

Im Python Interpreter (2.x)  
```
execfile('someFile.py')
```

Im Python Interpreter (3.x)  
```
exec(open('someFile.py').read())
```
&nbsp;

<a name="ch1-7"></a>
### 1.7 Decorators
`@staticmethod`  
The *staticmethod* decorator modifies a method function so that it does not use the self variable. The method function will not have access to a specific instance of the class. It behaves like a plain function except that you can call it from an instance or the class.  

`@classmethod`  
The *classmethod* decorator modifies a method function so that it receives the class object as the first parameter instead of an instance of the class. This method function will have access to the class object itself.  
The 'classmethod' decorator is used to create singleton classes. This is a python technique for defining an object which is also the one and only instance. This gives us a very handy, easy-to-read way to segregate attributes into a separate part of a class declaration.  
Generally, a function decorated with *@classmethod* is used for introspection of a class. An introspection method looks at the structure or features of the class, not the values of the specific instance.

&nbsp;

# Functions

&nbsp;

<a name="ch2-1"></a>
## 2.1 Basic Functions  

<a name="ch2-1-1"></a>
### 2.1.1 Funktion *id()*  
Die Identität einer Instanz dient dazu, sie von allen anderen Instanzen zu unterscheiden. Die Identität ist eine Ganzzahl, und sie ist innerhalb eines Programmes eindeutig. Die ``Identitätsfunktion id()`` liefert die Identität. So kann man prüfen, ob es sich um eine bestimmte Instanz handelt und nicht nur um eine mit dem gleichen Wert und Typ.

```
>>> x = 42
>>> id(x)
10107136
>>> y = x
>>> id(x), id(y)
(10107136, 10107136)
>>> y = 78
>>> id(x), id(y)
(10107136, 10108288)
```
Wir stellen fest, dass sich die Identität erst ändert, nachdem wir y einen neuen Wert zugewiesen haben. Die Identität von x bleibt gleich, d.h. der Speicherort von x wird nicht geändert.  

&nbsp;

<a name="ch2-1-2"></a>
### 2.1.2 Funktion *dir()*  
You can use the built-in 'dir()' function to list  the identifiers that a module defines. The identifiers are the functions, classes and variables defined in that module.  

When you pass a module name to the *dir()* function, it returns  the list of the names defined in that module. When no argument is applied to it, it returns the list of names defined in the current module.  

```
>>> import sys
>>> dir(sys)
['__doc__', '__stderr__', '__stdin__', '__stdout', '__getframe', 'api_version', 'argv', ...]
```

&nbsp;

<a name="ch2-1-3"></a>
### 2.1.3 Funktion *help()*  
This function invoked the built-in help system.  
If the argument is a string, then the string is looked up as the name of a module, function, class, method, keyword or documentation topic and a help page is printed on the console.  

This function is added to the built-in namespace by the *site* module.

&nbsp;

<a name="ch2-1-4"></a>
### 2.1.4 Funktion *type()*
Die Funktion *type(obj)* liefert die Klasse der Instanz 'obj' zurück.  

```
>>> x = [4,5,9]
>>> print type(x)
<type 'list'>

>>> y = "Hello"
>>> print type(y)
<type 'str'>

>>> v = 10
>>> print type(v)
<type 'int'>

>>> z = {'a':1, 'b':2}
>>> print type(z)
<type 'dict'>
```

&nbsp;

<a name="ch2-2"></a>
## 2.2 String Functions  
&nbsp;

**Konkatenation** (englisch: Concatenation)  

&nbsp;&nbsp;&nbsp; ``"Hello" + "World" -> "HelloWorld"``

**Indexing**  

&nbsp;&nbsp;&nbsp; ``"Python"[0] -> "P"``  

**Slicing**  
[2:4] bedeutet im folgenden Ausdruck, dass wir aus dem String "Python" einen Teilstring herausschneiden, der mit dem Zeichen des Index 2 (inklusive) beginnt und bis zum Index 4 (exklusive) geht:  

&nbsp;&nbsp;&nbsp; ``"Python"[2:4] -> "th"``

**Länge eines Strings**  

&nbsp;&nbsp;&nbsp; `len("Python") -> 6`  

&nbsp;


<a name="ch2-3"></a>
## 2.3 Object Oriented related Functions  

All of the basic factory functions (str, int, float, long, complex, unicode, tuple, list, dict, set) are effectively class names. You can therefore, use a test like `isinstance(myParam, int)` to confirm that the argument value provided to this parameter is an integer. An additional class, `basestring` is the parent class of both 'str' and 'unicode'.  

<a name="ch2-3-1"></a>
### 2.3.1 Funktion *issubclass(sub, sup)*  
Boolean function returns 'true' if the given subclass ``sub`` is a subclass of the upper-class ``sup``.

&nbsp;

<a name="ch2-3-2"></a>
### 2.3.2 Funktion *isinstance(obj, class)*  
Boolean function returns 'true' if ``obj`` is an instance of class ``class`` or is an instance of a subclass of `class`.  

&nbsp;

<a name="ch2-3-3"></a>
### 2.3.3 Funktion *super(type)*  
Function returns the superclass of the given type.

&nbsp;

# Listen

<a name="ch3-1"></a>
## 3.1 Basics

The list is a most versatile datatype available in Python which can be written as a list of comma-separated values (items) between square brackets. Important thing about a list is that items in a list need <u>not</u> be of the same type.  

```
>>> list1 = ['physics', 'chemistry', 1997, 2000];
>>> list2 = [1, 2, 3, 4, 5];
>>> list3 = ["a", "b", "c", "d"];
```

Similar to string indices, list indices start at 0 and lists can be sliced, concatenated and so on.  

```
>>> print "list1[0]: ", list1[0];
list1[0]: physics
>>> print "list2[1:5]: ", list2[1:5];
list2[1:5]: [2,3,4,5]
```

&nbsp;

<a name="ch3-2"></a>
## 3.2 *List* Functions

  - Delete list element  
     To remove a list element, you can use either the 'del' statement if you know exactly which element(s) you are deleting (by index) or the 'remove()' method if you do not know.  
     ```
      >>> del list[2]         ;# deleted the third items
      >>> list1.remove(2000)  ;# also deletes the third item
     ```
     **(!)** 'remove()' only deletes the <u>first appearance</u> of the item in the brackets.

  - Basic list operations  

     |Function   |Python expression   |Result   |  
     |:---|:---|:---:|  
     |Length   | **len([1,2,3])**  | 3  |  
     |Concatenation   | **[1,2,3]+[4,5,6]**   | [1,2,3,4,5,6]  |  
     |Repetition   | **['Hi!']*4**  | ['Hi!','Hi!','Hi!','Hi!']  |  
     |Membership   | **3 in [1,2,3]**  | True  |  
     |Iteration   | **for x in [1,2,3]: print x**  | 1,2,3  |   

  - Further functions  

     |Function   |description   |  
     |:---|:---|  
     |**max(list)**   | Returns item from list with max value  |  
     |**min(list)**   | Returns item from list with min value  |  
     |**list.append(obj)**   | Appends object 'obj' to list  |  
     |**list.count(obj)**   | Returns number of how many times 'obj' occurs in list  |  
     |**list.index(obj)**   | Returns the lowest index in list that 'obj' occurs  |  
     |**list.indert(index,obj)**   | Inserts object 'obj' into list at offset 'index'  |   

  - Copy/Compare List  
     ```
     >>> a = [1,2,3]
     >>> b = a        ;# Achtung: keine Kopie! Zeiger auf Inhalt von 'a'
     >>> b = a[:]     ;# Kopie von 'a' in 'b' (neuer Speicher wird angelegt)
     >>> a == b  
     True
     ```  

  - Looping through list
     ```
     for <var> in <list> :
          print <var>
     ```

  - Sorting list  
     ```
     >>> a = [1,4,3]
     >>> sorted(a)
     [1,3,4]
     >>> sorted(a, reverse=true)
     [4,3,1]
     ```  

  - String aus Liste / Liste aus String  
     ```
     >>> a = [1,2,3]
     >>> '.'.join(a)
     '1.2.3'
     >>> ':'.join(a)
     '1:2:3'

     >>> b = 'aa:bb:cc'
     >>> b.split(':')
     ['aa', 'bb', 'cc']
     ```

&nbsp;

# Dictionaries

Ein 'Dictionary' besteht aus Schlüssel-Objekt-Paaren, zu einem bestimmten Schlüssel gehört immer ein Objekt.  
```
>>> mydict = {}                          ;# leeres Dictionary
>>> mydict = {"key_01":"value_01"}       ;# Wert setzen
>>> mydict = {"key_x":"val_x", "key_y":"val_y"}

>>> len(mydict)                          ;# Anzahl der Schlüssel-Wert-Paaren
>>> del mydict[key_01]                   ;# Löschen Schlüssel+Objekt
>>> "k" in mydict                        ;# Prüfen auf Schlüssel
>>> "k" not in mydict

>>> mydict.clear()                       ;# Entfernt alle Elemente im dictionary
>>> mydict.get(key)                      ;# Gibt den 'Value' für 'key zurück
>>> mydict.has_key(key)                  ;# Gibt 'true' zurück falls 'key' vorhanden
>>> mydict.items()                       ;# Gibt Liste mit (key, value)-Paaren zurück
>>> mydict.keys()                        ;# Gibt Liste aller key's zurück
>>> mydict.values()                      ;# Gibt Liste aller value's zurück
```
&nbsp;

Iteration über ein Dictionary
```
>>> for key in mydict
        print mydict[key]
```
&nbsp;

Verschachtelte Dictionaries
```
>>> d = {}
>>> d['dict1'] = {}
>>> d['dict1']['innerkey'] = 'value'

>>> d = {'dict1' : {'innerkey' : 'value'}}
>>> d = {'dict1' : {'inkey1': val, 'inkey2' : val2}}

# Besserer bzw. sicherer Weg
# Anlegen:
>>> d['key1'] = {}
>>> d['key1']['innerkey'] = []
>>> d['key1']['innerkey'].append('value')

# Auslesen:
>>> d.get('key1', {}).get('innerkey')
# Sicherer, da bei Fehlen eines der 'keys' kein Fehler geworfen wird, sondern
# 'None' zurückgegeben wird.
```

&nbsp;

# How To's

<a name="ch5-1"></a>
## 5.1 File handling  

`open()` returns a file object and is most commonly used with two arguments:  
```
>>> open(filename, mode)
```

The first arguement is the ``filename``.  
The second argument describes in which way the file will be used. `mode` can be `r` when the file will only be read, `w` for only writing (an existing file with the same name will be erased) and `a` opens the file for appending.  
&nbsp;

For reading lines from a file, you can loop over the file object. This is memory efficient, fast, and leads to simple code:   
```
>>> f = open('workfile', 'r')
    for line in f:
       print line
```
&nbsp;


If you want to read all lines of the file in a list you can also use `f.readlines()`.
```
>>> lines = f.readlines()
```
&nbsp;

If you want to read in all lines of a file into one big string, you can use `f.read()`.
```
>>> text = f.read()
```
&nbsp;

To write the content of a string to the file you use `f.write(string)`  
```
>>> f.write(string)
```

&nbsp;

<a name="ch5-2"></a>
## 5.2 Regular Expressions  

<a name="ch5-2-1"></a>
### 5.2.1 Basics    

Das Modul `re` der Standardbibliothek bietet umfangreiche Möglichkeiten zum Arbeiten mit sogenannten 'regulären Ausdrücken'. In einem solchen regulären Ausdruck wird durch eine spezielle Syntax ein Textmuster beschrieben, das dann auf verschiedene Texte oder Textfragmente angewendet werden kann. Grundsätzlich gibt es zwei große Anwendungsbereiche von regulären Ausdrücken:  
1. Im ersten Bereich, beim sog. ``Matching`` wird geprüft, ob ein Textabschnitt auf das Muster des regulären Ausdruck passt oder nicht.  
2. Die zweite Einsatzmöglichkeit von regulären Ausdrücken ist das sog. ``Searching``, bei dem innerhalb eines größeren Textes nach Textfragmenten gesucht wird, die auf einen regulären Ausdruck passen.  

Innerhalb von regulären Ausdrücken haben zahlreiche Zeichen Sonderbedeutungen, so wie auch der Backslash ("\\"). Prinzipiell werden reguläre Ausdrücke in Python als Strings dargestellt. Bei Strings werden aber Backslashes als Escape-Zeichen benutzt. Das bedeutet aber, dass sie aus unserem regulären Ausdruck entfernt werden, bzw. mit dem folgenden Zeichen einer Sonderbedeutung zugeführt werden. Die beste Lösung besteht darin, 'Raw-Strings' zu verwenden, also einen String mit einem vorgestellten `r` zu markieren:  
```
>>> r"^a.*\.html$"
   # oder
>>> r"cat"
```

Im Beispiel verwenden wir die Methode `search` aus dem Modul `re`. Es ist die wohl am wichtigsten und am häufigsten benutzte Methode. Mittels `search(expr, s)` wird ein String s nach dem Vorkommen eines Teilstrings untersucht, der auf den regulären Ausdruck 'expr' passt. Der erste gefundene Teilstring wird zurückgeliefert. Im positiven Fall wird ein sog. Matching-Objekt zurückgeiefert, im negativen Fall ein 'none'.  

```
>>> if re.search("cat", "A cat and a rat can't be friends."):
        print "Der Ausdruck passt."  
   else:  
        print "Der Ausdruck passt nicht."
# Output: "Der Ausdruck passt."
```

&nbsp;

<a name="ch5-2-2"></a>
### 5.2.2 Syntax regulärer Ausdrücke  

Zeichenliterale innerhalb regulärer Ausdrücke sind case sensitive, d.h. dass der Ausdruck `r"python"` nicht auf den String "Python" passen würde.  

In regulären Ausdrücken können eine ganze Reihe von **Steuerungszeichen** verwendet werden:  

**(a) Beliebige Zeichen**  
Die einfachste Verallgemeinerung, die innerhalb eines regulären Ausdrucks verwendet werden kann, ist die Kennzeichnung eines beliebigen Zeichens durch einen Punkt. So passt der Ausdruck `r".ython"` sowohl auf "python", "Python" als auch "Jython", nicht jedoch auf "Blython", da es sich nur um ein einzelnes beliebiges Zeichen handelt.  

**(b) Zeichenklassen**  
Abgesehen davon, ein Zeichen ausdrücklich als beliebig zu kennzeichnen, ist es auch möglich, eine Klasse von Zeichen  vorzugeben, die an dieser Stelle vorkommen dürfen.  

`r"[jp]ython"`  
Der Ausdruck lässt nur die Buchstaben 'j' und 'p' als erstes Zeichen des Wortes zu.  

`r"[A_Z]ython"`  
Der Ausdruck lässt den Bereich zwischen A und Z in Großbuchstaben zu.  

`r"[A_Ra-r]ython"`  
Um mehrere Bereiche zuzulassen, werden diese hintereinander geschrieben.  

`r"[0-9]ython"`  
Auch Ziffernbereiche können als Zeichenklasse verwendet werden.  

`r"[pP]ython"`  
Zeichen oder Zeichenbereiche können auch ausgeschlossen werden. Hier ist jedes Zeichen erlaubt, außer p und P.  

Innerhalb einer Zeichenklasse gibt es, abgesehen vom Bindestrich und Zirkumflex, keine Zeichen mit spezieller Bedeutung.  
Ein Punkt in einer Zeichenklasse ist tatsächlich ein Punkt und nicht etwa ein beliebiges Zeichen.  

**(c) Quantatoren**  
Quantatoren sind spezielle Zeichen, die hinter ein einzelnes Zeichenliteral oder eine Zeichenklasse geschrieben werden und kennzeichnen, wie oft diese auftreten dürfen.  


|Quantator   |Beschreibung   |  
|:---|:---|  
|? |Das vorangegangene Zeichen bzw. die vorangeganene Zeichenklasse darf entweder keinmal oder einmal vorkommen. |  
|* |...darf beliebig oft hintereinander vorkommen, das heißt unter anderem, dass sie auch weggelassen werden kann. |  
|+ |...darf beliebig oft hintereinander vorkommen, mindestens aber einmal. |   
|{anz} |...muss exakt 'anz'-mal vorkommen. |  
|{min,} |...muss mindestens 'min'-mal vorkommen. |  
|{,max} |...darf maximal 'max'-mal vorkommen. |  
|{min, max} |...muss mindestens 'min'-mal und darf 'max'-mal vorkommen. |   

&nbsp;

```
r"P[Yy]?thon"
```
&rarr; Ausdruck erwartet an der zweiten Stelle des Wortes ein höchstens einmaliges Auftreten des großen oder kleinen 'Y'.  

```
r"P[Yy]{,2}thon"
```
&rarr; Ausdruck erwartet an der zweiten Stelle des Wortes maximal zwei jeweils große oder kleine 'Y'.  

&nbsp;

**(d) Weitere Sonderzeichen**  
Für gewisse Einsatzgebiete wird es unbedingt verlangt, Regeln aufzustellen zu können, die über bloße Zeichenebene hinausgehen. Die hier gezeigten Sonderzeichen beziehen sich hauptsächlich auf das Matching von regulären Ausdrücken.  


|Zeichen   |Beschreibung   |  
|:---|:---|  
|\A |Passt nur am Anfang eines Strings. |  
|\b |Passt nur am Anfang oder Ende eines Wortes. |  
|\B |Passt nur, wenn es sich nicht um den Anfang oder das Ende eines Worted handelt. |  
|\Z |Passt nur am Ende eines Strings. |  
|^ |Passt nur am Anfang eines Strings. |  
|$ |Passt nur am Ende eines Strings. |  

&nbsp;

```
r"\APython\Z"
```
&rarr; Reg. Ausdruck passt auf die Strings "Python", nicht jedoch bei den Strings "abcPython" oder "Pythonabc".  
&nbsp;  


|Zeichen   |Beschreibung   |  
|:---|:---|  
|\d |Passt auf alle Zeichen, die Ziffern des Dezimalsystems sind. Äquivalent zu \[0-9\]. |  
|\D |Passt auf alle Zeichen, die nicht Ziffern des Dezimalsystems sind. Äquivalent zu \[^0-9\]. |  
|\s |Passt auf alle Whitespace-Zeichen. Äquivalent zu [\t \n \r \f \v]. |  
|\S |Passt auf alle Zeichen die kein Whitespace sind. Äquivalent zu [^ \t \n \r \f \v]. |  
|\w |Passt auf alle alphanumerischen Zeichen und den Unterstrich. Äquivalent zu [a-zA-Z0-9_]. |  
|\W |Passt auf alle Zeichen die nicht alphanumerischen und kein Unterstrich sind. Äquivalent zu [^a-zA-Z0-9_]. |   

&nbsp;  

```
r"P\w*yth\dn"
```
&rarr; Reg. Ausdruck passt auf die Wörter "Pyth0n" oder "P_th1n", bspw jedoch nicht auf "Python".  
&nbsp;  

&nbsp;

[Back](../)
