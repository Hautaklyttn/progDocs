---
layout: default
---

[Back](../)

&nbsp;

# Python
---

&nbsp;

# Basics

&nbsp;

<a name="ch1-1"></a>
### 1.1 Geschichte  
Die Sprache wurde Anfang der 1990er Jahre von Guido van Rossum am Zentrum für Mathematik (Centrum voor Wiskunde en Informatica) in Amsterdam entwickelt. Ursprünglich war sie als Nachfolger für die Lehrsprache ABC entwickelt worden und sollte auf dem verteilten Betriebssystem Amoeba laufen. Guido van Rossum hatte auch an der Entwicklung der Sprache ABC mitgewirkt, so dass seine Erfahrungen mit ABC auch in Python einflossen.  

&nbsp;

<a name="ch1-2"></a>
### 1.2 Der Interpreter, eine interaktive Shell  
Im Englischen steht das Wort "shell" für eine Schale, einen Panzer oder ganz allgemein eine Hülle oder Schutzhülle. "Shell" bezeichnet auch ein Schneckenhaus und das Gehäuse, das eine Muschel umschließt. Ebenso liegt eine Shell auch zwischen einem Betriebssystem und dem Benutzer. Wie eine Muschelschale schützt sie zum einen das Betriebssystem vor dem Benutzer und gleichzeitig erspart sie dem Benutzer die Benutzung der "primitiven" und schwer verständlichen Basisfunktionen, indem sie ihm komfortable Befehle zur Kommunikation mit dem Computer zur Verfügung stellt.  

Auch die Programmiersprache Python bietet dem Anwender eine komfortable Kommandozeilen-Schnittstelle, die sogenannte Python-Shell, die man manchmal auch als interaktive Python-Shell bezeichnet. Man könnte meinen, dass es sich bei dem Begriff "interaktive Shell" um eine Tautologie handelt, da ja, so wie wir es oben beschrieben haben, Shells immer interaktiv sind. Dies ist jedoch nicht so: Es gibt auch vor allem im Umfeld von Linux und Unix Shells, die als Subshell aufgerufen werden und nicht interaktiv ausgeführt werden.  

Man kann Python im interaktiven Modus aufrufen, indem man den Interpreter in einer Linux-Shell (Bash-Shell) ohne Parameter aufruft. Also  
```js
>>> python
```

&nbsp;

Zweite Möglichkeit der interaktiven Arbeit ist der Online-Interpreter:  
[&rarr; &nbsp; Link](http://www.python-online.ch/pyonline/PyOnline.php)  

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
i = 42		   # Typ wird implizit auf Integer gesetzt
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
**Python wird zuerst ein neues Integer-Objekt mit dem Inhalt 78 erzeugen und dann wird die Referenz von y auf dieses Objekt geändert. Wichtig ist dabei, dass x nach wie vor das alte Objekt referenziert, d.h. der Wert ist nach wie vor 42**  (&rarr; s. Kapitel 2.1: Funktion id() zum Prüfen der Identität).

Wird x jetzt ein String zugewiesen, würde das Integer-Objekt "42" verwaist. Es muss von Python entfernt werden, da es von keiner anderen Variable referenziert wird.

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

Achtung:
> Wie in Java aber nicht wie in C oder C++, können Strings in Python nicht verändert werden. Versucht man eine indizierte Position zu ändern, erzeugt man eine Fehlermeldung.

&nbsp;



&nbsp;

# Basic Functions

&nbsp;

<a name="ch2-1"></a>
### 2.1 Funktion *id()*  
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

<a name="ch2-2"></a>
### 2.2 String Funktionen  
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

[Back](../)
