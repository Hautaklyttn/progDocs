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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.4 The Object Model</font>](#ch1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.5 Variablen in Python</font>](#ch1-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.6 Strings</font>](#ch1-6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.6.1 Execute String containing Python code</font>](#ch1-6-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.7 Aufruf eines Python-Skripts (*.py)</font>](#ch1-7)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.8 Decorators</font>](#ch1-8)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9 `import`</font>](#ch1-9)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10 `call-by-value` / `call-by-reference`</font>](#ch1-10)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.11 Variable Scope</font>](#ch1-11)  

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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.3 Sockets</font>](#ch5-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.4 Code Quality Metrics</font>](#ch5-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.5 Access Windows Applications using COM</font>](#ch5-5)  

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
### 1.4 The Object Model  

**Everything in python is an object**. Every variable you make is an object, every operation you execute is between objects.  `int`, `float`, functions, and anything else you can thing of: all objects inherit from python's base object class, unsurprisingly named object. What does this mean?  
> In Python, primitive data types are in fact not very primitive at all, and are instead feature rich in comparison to their counterparts in lower level languages.  

Let's explore this a little bit by just looking at an integer. We'll create an `int`, then see what attributes it has by calling the `dir` function. When `dir` is called on an object, it recursively searches all the attributes of the argument and it's parents or base classes.  
```py
>>> n = 1
>>> dir(n)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getnewargs__', '__gt__', '__hash__', '__index__', '__init__', '__init_subclass__', '__int__', '__invert__', '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__', '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__', '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__', '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__', 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag', 'numerator', 'real', 'to_bytes']
```
There's a lot more to an integer than just a value. In lower level languages, like C, C++, or Java, primitive types refer to sections of memory, designated to contain a specifc value that can be directly manipulated in assembly code or even transistor level logic in CPUs. Python sits at a much higher abstraction level. Though python is slower than the aforementioned languages, the programmer doesn't have to deal with problems like overflow, underflow, or invalid type casting as all of this is abstracted away through objects. Some of the attributes listed through `dir(int)` are class specific to `int`, and some are inherited from `object`. Let's see what attributes object by calling `dir` on the static type itself.  
```py
>>> dir(object)
['__class__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__']
```

&nbsp;

**Getters and Setters**  
Python additionally has a set of built in set of methods for getting, setting, and deleting attributes. The `object` base class has the following getter and setter methods which are wrapped by built-in python functions.

|Object Method|Built-in Function|Description|  
|:---|:---|:---|  
|`object.__getattribute__('name')`|`getattr(object, 'name')`|Gets attribute|
|`object.__setattr__('name', value)`|`setattr(object, 'name', value)`|Sets attribute to value|
|`object.__delattr('name')`|`delattr(object, 'name')`|Deletes attribute|
|N/A|`hasattr(object, 'name')`|Checks if an object has an attribute.|  

&nbsp;

**Special Object Functions**  
In order to enable consistent usage across all of the different objects in Python, they all utilize the same special methods denoted with two underscores on either side `__func__`. Overriding these objects in your own implementations can lead to neat and concise code for complex functions. They can be overriden by defining the `__func__(self, [args])` function within an object. These functions are often refered to as **"magic" functions**.  

The first thing to know about *special object functions* is that they are meant to be called by the Python interpreter, and not by you. You don’t write `my_object.__len__()`. You write `len(my_object)` and, if `my_object` is an instance of a user-defined class, then Python calls the `__len__` instance method you implemented.  

More often than not, the special method call is implicit. For example, the statement `for i in x:` actually causes the invocation of `iter(x)`, which in turn may call `x.__iter__()` if that is available.  

Normally, your code should not have many direct calls to special methods. Unless you are doing a lot of metaprogramming, you should be implementing special methods more often than invoking them explicitly. The only special method that is frequently
called by user code directly is `__init__`, to invoke the initializer of the superclass in your own `__init__` implementation.  

If you need to invoke a special method, it is usually better to call the related built-in function (e.g. `len`, `iter`, `str`, etc). These built-ins call the corresponding special method, but often provide other services and — for built-in types — are faster than method calls.  

|Attribute|Built-In Accessor|Description|  
|:---|:---|:---|  
|`__new__`|N/A|Called when creating a new instance of an object|  
|`__init__`|N/A|Called when instantiating a new instance of an object, after `__new__`|  
|`__class__`|`type(obj)`|Returns the type of a given object.|  
|`__str__`|`str(obj)`|Converts object to a string. This is called when printed.|  
|`__repr__`|`repr(obj)`|Returns a representation of the object used in the python shell.|  
|`__doc__`|`help(obj)`|Gives documentation for the given type.|  
|`__hash__`|`hash(obj)`|Custom hash function for the object.|  
|`__get__`|N/A|Invoked every time an object is accessed. Used by function objects to make them callable. Similar definition for `__set__`|  
|`__eq__`|`==`|Provides comparison binary operator. Other comaprison operators are `__lt__`, `__le__`, `__ne__`, `__ge__`, `__gt__`|  
|`__add__`|`add(a, b)`, `+`|Overrides math functionality. Others are `__sub__`, `__mul__`, `__abs__`, `__floordiv__`, `__truediv__`, `__pow__`, etc.|  
|`__getitem__`|`object[ind]`|Returns value of an object at a certain index|  
|`__and__`|`and`|Returns logical and. Other logical operators are `__or__`, `__not__`, `__xor__`, `__lshift__`, etc.|  
|`__contains__`|`val in obj`|Checks to see if an object contains a value using `in` keyword.|  
|`__next__`|`next(obj)`|Yields next value of an object.|  
|`__yield__`|`iter(obj)`, `for _ in obj`|Returns an iterator over the values of the object.|  

You can find more operator attributes here: [https://docs.python.org/3/library/operator.html](https://docs.python.org/3/library/operator.html).

&nbsp;

<a name="ch1-5"></a>
### 1.5 Variablen in Python  
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

<a name="ch1-6"></a>
### 1.6 Strings  
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

<a name="ch1-6-1"></a>
#### 1.6.1 Execute String containing Python code  

For statements use `exec(string)` (Python 2/3) or `exec string` (Python 2):  

```py
>>> mycode = 'print "hello world"'
>>> exec(mycode)
'hello world'
```
When you need the value of an expression, use `eval (string)`:  

```py
>>> x=eval("2+2")
>>> x
4
```

&nbsp;

<a name="ch1-7"></a>
### 1.7 Aufruf eines Python-Skripts (\*.py)

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

<a name="ch1-8"></a>
### 1.8 Decorators
`@staticmethod`  
The *staticmethod* decorator modifies a method function so that it does not use the self variable. The method function will not have access to a specific instance of the class. It behaves like a plain function except that you can call it from an instance or the class.  

`@classmethod`  
The *classmethod* decorator modifies a method function so that it receives the class object as the first parameter instead of an instance of the class. This method function will have access to the class object itself.  
The 'classmethod' decorator is used to create singleton classes. This is a python technique for defining an object which is also the one and only instance. This gives us a very handy, easy-to-read way to segregate attributes into a separate part of a class declaration.  
Generally, a function decorated with *@classmethod* is used for introspection of a class. An introspection method looks at the structure or features of the class, not the values of the specific instance.

&nbsp;

<a name="ch1-9"></a>
### 1.9 `import`  
- Use classes & functions defined in another file  
- A python module is a file with the same name (plus the *.py* extension)  

Three formats of the command:  
1. `import somefile`
   - Everything in *somefile.py* gets imported.
   - To refer to sth in the file, append the text 'somefile.' to the front of its name, e.g.  
     ```py
     somefile.className.method('abc')
     somefile.myFunc('123')
     somefile.var123
     ```
   &nbsp;
2. `from somefile import *`
   - Everything in *somefile.py* gets imported.
   - To refer to sth in the module, just use its name. Everything in the module is now in the current namespace, e.g.  
     ```py
     className.method('abc')
     myFunc('123')
     var123
     ```
   &nbsp;  
3. `from somefile import className`  
   - Only the item 'className' gets imported.  
   - After import only 'className' can be used without module prefix.

&nbsp;  

*Where does python look for module files?*  
The list of directories where Python will look for the files to be imported is *sys.path*. This is just a variable named 'path' stored inside the 'sys' module, i.e.  
```py
import sys
sys.path
   => ["", /Library/Frameworks/..., ...]
```  

To add a directory of your own to this list, append it to the list:  
```py
sys.path.append('/my/new/path')
```

&nbsp;

<a name="ch1-10"></a>
### 1.10 `call-by-value` / `call-by-reference`  
Je nach Programmiersprache gibt es unterschiedliche Möglichkeiten wie Argumente übergeben werden:

**call-by-value**: Hier wird funktionsintern mit Kopien der als Parameter übergebenen Instanzen gearbeitet.

*Vor- Nachteile*: Eine Funktion kann keine Änderungen von Instanzen aus dem Hauptprogramm bewirken, erzeugt jedoch unter Umständen einen erheblichen Overhead.

**call-by-reference**: Dabei wird funktionsintern mit Referenzen (Pointer) auf die im Hauptprogramm befindlichen Instanzen gearbeitet.

*Vor- Nachteile*: “Schlanke” Calls da keine Daten erzeugt werden, jedoch besteht die Gefahr, dass eine Funktion Instanzen aus dem Hauptprogramm ändern kann.

Python verwendet diesbezüglich eine <u>Mischform</u>.

Eine **call-by-reference** gibt es bei <u>veränderbaren Datentypen</u> (==**mutable objets**) (z.B. `list` oder `dict` aber auch den meisten anderen Objekten).  

```py
>>> def test(liste):
...     liste += [5,6,7]
...
>>> zahlen = [1,2,3]
>>> print zahlen
[1, 2, 3]
>>> test(zahlen)
>>> print zahlen
[1, 2, 3, 5, 6, 7]
>>>
```
Man sieht die (ungewollte) Veränderung der Liste im Hauptprogramm. Vermeidung einfach durch Kopieren beim Funktionsaufruf:
```py
>>> test(zahlen[:])
>>> print zahlen
[1, 2, 3]
```

Bei <u>unveränderbaren Datentypen</u> (z.B. Zahlen, Strings oder Tupel) wird ein **call-by-value** verwendet.
```py
>>> def test_zahl(zahl):
...    zahl += 2
...
>>> a = 2
>>> print a
2
>>> test_zahl(a)
>>> print a
2
```
**call-by-value** also bei den Datentypen `int`, `float`, `complex`, `string`, `tuple`, `frozen set`, `bytes` (== **immutable objects**).  

&nbsp;

<a name="ch1-11"></a>
### 1.11 Variable scope  

In python, scopes are defined by `dict` like namespaces, similar to those found in objects. Within objects (and thus within functions), different namespaces are applied than the global python namespace. When python looks up the value attributed to a variable name, it first looks up the name in it's immediate scope by checking the namespace of the object the function is in. If it doesn't find the given variable there, it proceeds down the call stack searching for it, until it finds the variable or reaches the global scope and can't find it.  

```py
x = "global"

def fn1():
    x = "local"
    print(x)

def fn2():
    print(x)

print(x)    # global
fn1()       # local
fn2()       # global
```
You can access the local namespace by calling the `locals()` function, or the global namespace by calling the `globals()` function, both of which return key attribute dictionaries.  

&nbsp;

**`nonlocal` keyword**  
The `nonlocal` keyword in python can be used in nested functions to make a given variable refer to one that is used in a different scope. This essentially binds the variable in local scope to the variable in the next higher level scope where it is defined.  
```py
def outer():

    x = "outer"

    def inner():
        nonlocal x
        x = "inner"
        print("From Inner:", x)

    inner()
    print("From Outer:", x)

outer()

# Output:
# From Inner: inner
# From Outer: inner
```
This is because the variable `x` is set to refer to the namespace of `outer` with the `nonlocal` keyword. Thus, `x` gets set to `"inner"` in the namespace of `outer`. If `nonlocal` was not present, we would instead get the expected result of `"inner"` from `inner` and `"outer"` from `outer`.  

&nbsp;  

**`global` keyword**  
While `nonlocal` can refer to external scopes, the keyword `global` can be used to make variables refer to their versions in the global namespace. The `global` key word makes a given variable refer to the global scope. Be careful though the `global` and `nonlocal` descriptors only take effect in a given scope. The following example demonstrates this.  

```py
x = "global"

def outer():
    x = "outer"
    def inner():
        global x
        x = "inner"
        print("From Inner:", x)
    inner()
    print("From Outer:", x)

outer()
print("From Global:", x)

# Output:
# From Inner: inner
# From Outer: outer
# From Global: inner
```
Note that in the scope of `outer` the variable is unchanged. This is because the binding of `global` only takes effect within the scope it is used. As expected, in `inner`, x will refer to the global variable and change it to `"inner"`.



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

<a name="ch5-3"></a>
## 5.3 Sockets  

Das Modul *socket* der Standardbibliothek bietet grundlegende Funktionalität zur Netzwerkkommunikation.  

Die Idee, die hinter der *socket* API steckt, ist die, dass das Programm, das Daten über die Netzwerkschnittstelle senden oder empfangen möchte, dies beim Betriebssystem anmeldet und von diesem einen sogenannten 'Socket' (dt. Steckdose) bekommt. Über diesen Socket kann das Programm jetzt eine Netzwerkverbindung zu einem anderen Socket aufbauen. Dabei spielt es keine Rolle, ob sich der Zielsocket auf demselben Rechner, einem Rechner im lokalen Netzwerk oder einem Rechner im Internet befindet.  

&nbsp;

![so](../assets/pics/sockets_py.png)  

&nbsp;

Eine Kommunikation zwischen zwei Rechnern A und B (genauer: zwischen Prozessen auf diesen Rechnern) benötigt die IP-Adressen der beteiligten Rechner sowie die Ports:  
**A** (IP-Adresse, Port) &harr; **B** (IP-Adresse, Port)  

Ein Server ist unter einer bestimmten Adresse im Netzwerk erreichbar und operiert passiv, das heißt, er wartet auf eingehende Verbindungen. Sobald eine Verbindungsanfrage eines Clients eintrifft, wird, sofern der Server die Anfrage akzeptiert, ein neuer Socket erzeugt, über den die Kommunikation mit diesem speziellen Client läuft.  

*client endpoints* : endpoint of a conversation  
*server socket* : more like a switchboard operator  

- Socket vs Webservice
  In a nutshell sockets are what web services use to communicate with their client. You can send any random bytes over a socket. When you use a web service, data is sent usding a standard format that makes it easy for the client to parse the data. Additionally using raw sockets gives you the benefit of control.  

&nbsp;

- Ablauf **Verbindungsaufbau**  
  Zunächst wird im Serverprogramm der sogenannte *Verbindungssocket* erzeugt. Das ist ein Socket der ausschließlich dazu gedacht ist, auf eingehende Verbindungen zu horchen und diese ggfs. zu akzeptieren. Über den Verbindungssocket läuft keine Kommunikation. Durch Aufruf der Methoden *bind* und *listen* wird der Verbindungssocket an eine Netzwerkadresse gebunden und dazu instruiert, nach einkommenden Verbindungsanfragen zu lauschen.  

  Nachdem eine Verbindungsanfrage eingetroffen ist und mittels *accept* akzeptiert wurde, wird ein neuer Socket, der sog. 'Kommunikationssocket' erzeugt. Über einen solchen Kommunikationssocket wird die vollständige Kommunikation zwischen Server und Client über Methoden wie *send* und *recv* abgewickelt. Beachten Sie, dass ein Kommunikationssocket immer nur für einen verbundenen Client zuständig ist.  

  Die Struktur des Client ist vergleichsweise einfach. So gibt es bspw. nur einen Kommunikationssocket, über den mithilfe der Methode *connect* eine Verbindungsanfrage an einen bestimmten Server gesendet werden kann. Danach erfolgt, ähnlich wie beim Server, die tatsächliche Kommunikation über Methoden wie *send* oder *recv*.  
  &nbsp;

  (1) Server
  ```py
  import socket

  host=''
  port=45000

  s=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  s.bind((host,port))
  s.listen(1)

  try:
      while True:
         komm, addr = s.accept()
         while True
            data=komm.recv(1024)

            if not data
               komm.close()
               break
            
            print "[%s]%s % (addr[0], data)
            nachricht = raw_input("Antwort:")
            komm.send(nachricht)
   finally:
      s.close()
  ```

  - Es wird "AF_INET" für das IPv4-Protokoll und "SOCK_STREAM" für die Verwendung von TCP übergeben. Damit ist der Socket nur in seiner Reinform instanziiert. Der Socket muss an eine IP-Adresse und einen Port gebunden werden.
  &nbsp;

  (2) Client
  ```py
  import socket

  ip=raw_input("IP-Adresse: ")
  s=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  s.connect((ip,50000))

  try
     while True:
        nachricht=raw_input("Nachricht:")
        s.send(nachricht)
        antwort=s.recv(1024)
        print "[%s] %s" % (ip,antwort)
   finally
      s.close()
  ```  
  - Auf der Clientseite wird der instanziierte Socket s  durch Aufruf der Methode *connect* mit dem Verbindungspartner verbunden. Die Methode *connect* verschickt genau die Verbindungsanfrage, die beim Server durch *accept* akzeptiert werden kann. Wenn die Verbindung abgelehnt wurde, wird eine Exception geworfen.  
  - In Python, you use `socket.setblocking(0)` to make it <u>non-blocking</u>. The major mechanical difference is that *send*, *recv*, *connect* and *accept* can return without having done anything.
&nbsp;

&nbsp;

<a name="ch5-4"></a>
## 5.4 Code Quality Metrics  
There are several popular Python tools that measure various metrics for Python developes, ranging from general code quality to specific metrics, like duplicated code or complexity. You can measure the cyclomatic complexity of your code with either *pygenie* or *pymetrics*.  

*What is your cyclomatic complexity?*  
Cyclomatic complexity is a software metric, developed by Thomas J. McCabe in 1976, to determine a program's complexity. The metric measures the number of linearly independent paths, or branches, through source code. According to McCabe, it is best to keep the complexity of a method below 10. This is important because research into human memory has determined that 7 (plus or minus 2) is the magical number of items that a human can hold in short term memory.  

If a developer is working on code that has 50 linearly independent paths, then they are roughly exceeding five times the capacity of short term memory in keeping track of what is occuring in that method.  Simpler methods that don't tax all of a human's short term memory are easier to work with  and have been proven to be less error prone. You can find a strong correlation between cyclomatic complexity and faultiness.  

&nbsp;

<a name="ch5-5"></a>
## 5.5 Access Windows Applications using COM  
Python has the "Python for Windows Extension" package known as *pywin32* that allows us to easily access Window's component object model (COM) and control Microsoft applications via Python.  

All of these applications start with similar imports and process for activating an application. Here is a short example of opening up Excel:  

```py
# Importieren des COM-Moduls
import win32com.client as win32    

# Erstellen eines COM-Objekts
excel=win32.gencache.EnsureDispatch ("Excel.Application")

# Excel startet sichtbar auf
excel.visible=True

# Erstellen eines neuen 'Workbooks'
wb=excel.Worksbooks.Add()
ws=wb.Worksheets("<name_tab>")

# Öffnen Workbook
wb=excel.Workbooks.Open("test_file.xlsx")

# Speichern+Schließen
wb.SaveAs("test_file.xlsx")
excel.Application.Quit()

# Neues Worksheet
ws_new=wb.Worksheets.Add()  # Werden vorne eingefügt
ws_new.Name="MyNewSheet"    # Worksheet umbenennen

# Zellenwert ändern
ws_new.Cells(2,2).Value="Eintrag xy"

# Farbe in Zelle ändern
ws_new.Cells(3,3).Interior.ColorIndex=#000000

# Zellenwert auslesen
value=ws_new.Cells(2,2).Value
```

&nbsp;

[Back](../)
