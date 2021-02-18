---
layout: default
---

{::options parse_block_html="true" /}  

[Back](../)  

&nbsp;

# C und C++
---  

&nbsp;

### 1. Basics    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 Eigenschaften von C</font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 C und C++</font>](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3 L- und R-Werte</font>](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.4 Auswertungsreihenfolge</font>](#ch1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.5 Headers und Libraries</font>](#ch1-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.6 Memory Management - 'Heap' vs 'Stack'</font>](#ch1-6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.7 Die Funktion `main`</font>](#ch1-7)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.8 Übersicht Datentypen in C</font>](#ch1-8)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9 Threads und Prozesse</font>](#ch1-9)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10 Benutzerdefinierte Datentypen</font>](#ch1-10)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10.1 `typedef`</font>](#ch1-10-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10.2 `enum`</font>](#ch1-10-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10.3 `struct`</font>](#ch1-10-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10.4 `union`</font>](#ch1-10-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.11 Precompiled Header</font>](#ch1-11)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.12 'Header Guard' (oder 'Include Guard')</font>](#ch1-12)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.13 'Calling Convention' (`__stdcall`)</font>](#ch1-13)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.14 Namespaces</font>](#ch1-14)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.15 `extern c` in C++</font>](#ch1-15)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.16 'Forward Declaration' in C++</font>](#ch1-16)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.17 'Function Prototype' and Definition in C</font>](#ch1-17)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.18 Präprozessor in C/C++</font>](#ch1-18)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.19 'Name Mangling' (or 'Name decoration')</font>](#ch1-19)  

### 2. Arrays
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Basics</font>](#ch2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.2 Übergabe von Arrays</font>](#ch2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3 Übergabe von Zeichenketten</font>](#ch2-3)  


### 3. Pointer
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 Referencing and Dereferencing</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 Addition und Subtraktion</font>](#ch3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.3 Call-by-Value</font>](#ch3-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.4 Call-by-Reference</font>](#ch3-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.5 Pointer auf Pointer</font>](#ch3-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.6 Pointer auf Funktionen</font>](#ch3-6)  

### 4. Pointer und Arrays   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.1 Vergleich von char-Arrays und Pointern auf Zeichenketten</font>](#ch4-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.2 Das Schlüsselwort `const` bei Pointern und Arrays</font>](#ch4-2)  

### 5. Programmsyntax und -semantik   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.1 Der Bedingungsoperator `A ? B : C`</font>](#ch5-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.2 `switch - case`</font>](#ch5-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.3 Das Schlüsselwort `extern`</font>](#ch5-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.4 Das Schlüsselwort `static`</font>](#ch5-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.5 `printf` Formatierungszeichen</font>](#ch5-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.6 `True` and `False` in C</font>](#ch5-6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.7 Konstruktor in C++</font>](#ch5-7)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.8 Das Schlüsselwort `pragma`</font>](#ch5-8)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.9 `Handle` in C++</font>](#ch5-9)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.10 'Exceptions' - `Try / Catch`</font>](#ch5-10)  

### 6. Bibliotheken, API's und *make*   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.1 Library Basics</font>](#ch6-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.2 [Win API] `#define DECLARE_HANDLE(n)`</font>](#ch6-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.3 [Win API] `HWND` (Fenster Handle)</font>](#ch6-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.4 'The C++ Standard Template Library' (Container-Klasse)</font>](#ch6-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.5 [make] Call 'Makefile' in Subdirectory</font>](#ch6-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.6 String</font>](#ch6-6)  

### 7. How To's & Special Syntax   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.1 Emulation</font>](#ch7-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.2 Code optimization turned off for debugging in 'Release' version</font>](#ch7-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.3 Digital Filter Implementation</font>](#ch7-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.4 Access file in .exe directory</font>](#ch7-4)  

### 8. Warnings and Errors  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">8.1 'Warning': no previous prototype for \<function\></font>](#ch8-1)  

&nbsp;

---  

&nbsp;

# Basics

&nbsp;

<a name="ch1-1"></a>
### 1.1 Eigenschaften von C

C ist eine relativ "maschinennahe" Sprache. C arbeitet mit denselben Objekten wie der Prozessor, nämlich mit **Zahlen** und **Adressen**. Auch Zeichen  werden als Zahlen gesehen, boolesche Variablen gibt es nicht und die Aufzählungskonstanten von Aufzählungstypen entsprechen ganzen Zahlen. Letztlich arbeitet C mit  
- verschiedenen Integer-Datentypen,  
- verschiedenen Gleitpunkt-Datentypen,  
- zusammengesetzten Datentypen wie  
   - Strukturen,
   - Unionen,  
   - Bitfeldern,  
- sowie Adressen.  

Die Sprache C erlaubt eine **hardwarenahe Programmierung** unter anderem durch direkte Zugriffe auf Adressen im Speicher oder durch Bitoperationen. C-Compiler unterstützen oftmals auch - in nicht standardisierter Weise - den Zugriff auf Hardware-Register.

C enthält die Elemente der **Strukturierten Programmierung**. C hat ein **Typkonzept**, das allerdings **nicht streng** ist. Der Compiler selbst führt  viele **implizite Typwandlungen** u.a. bei Zuweisungen durch. Bei unverträglichen Datentypen werden allerdings keine automatischen Umwandlungen durchgeführt, sondern eine Fehlermeldung erzeugt.

&nbsp;

<a name="ch1-2"></a>
### 1.2 C und C++

C++ ist eine Weiterentwicklung von C. C++ wurde entworfen, um zusätzlich zum klassischen C-Programmierstil  
- ein objektorientiertes Programmieren zu unterstützen  
- und ein **strenges Typkonzept für selbst definierte Datentypen. die Klassen**, zu realisieren, bei dem für einen Datentyp nur definierte Operationen zulässig sind. Hierbei darf der Compiler nur sehr eingeschränkte implizite Typwandlungen durchführen, ansonsten muss er Typverletzungen anzeigen.  

Während C als "Super-Assembler" für hardwarenahe Software entwickelt wurde, liegt die Zielrichtung bei der Entwicklung von C++ darin, dem Programmierer neue Sprachmittel wie z.B. Klassen in die Hand zu geben, um die Anwendungsprobleme zu formulieren.  

Der ANSI-C Standard revidierte ursprüngliche Inkompatibilitäten von C und C++, so dass C++ so nahe an C ist wie möglich. Eine hundertprozentige Kompatibilität ist jedoch nicht das Ziel, weil C++ eine höhere Typsicherheit anstrebt als C.  

&nbsp;

![01](../assets/pics/stammbaum.png)  
C in der Verwandschaftstafel höherer Programmiersprachen  

&nbsp;

![011](../assets/pics/c_timeline.png)  
Early C, UNIX und zugehörige Hardware

&nbsp;

![012](../assets/pics/later_c.png)  
Later C and C++  

&nbsp;

Sprachen und ihr Einsatzbereich:  
- `C` - systems programming, embedded systems
- `Objective C` - programming apps, IOS/OSX  
- `Ada` - real-time systems, aerospace, defense  
- `Cobol` - business programming  
- `Fortran` - scientific, parallel programming  
- `C++` - game programming  
- `Python` - scientific programming  

&nbsp;

<a name="ch1-3"></a>
### 1.3 L- und R-Werte  

Ausdrücke haben eine unterschiedliche Bedeutung, je nachdem, ob sie links oder rechts vom Zuweisungsoperator stehen. Im Beispiel  
> a = b  

steht der Ausdruck auf der rechten Seite für einen Wert, während der Ausdruck auf der linken Seite die Stelle angibt, an der der Wert zu speichern ist.

> Ein **Ausdruck** stellt einen **L-Wert** (**lvalue** oder **left value**) dar, wenn er sich auf ein **Speicherobjekt** bezieht. Ein solcher Ausdruck kann links und rechts des Zuweisungsoperators stehen.  

> Ein **Ausdruck** der keinen L-Wert darstellt, stellt einen **R-Wert** (**r-value** oder **right value**) dar. Er bezieht sich nicht auf ein **Speicherobjekt**. Er darf nur rechts des Zuweisungsoperators stehen. Einem R-Wert kann man also nichts zuweisen.  

Steht ein L-Wert rechts neben dem Zuweisungsoperator, so wird dessen Namen bzw. Adresse benötigt, um an der entsprechenden Speicherstelle den Wert der Variablen abzuholen.  

&nbsp;

````c  
int i;
int * ptr;
````

![02](../assets/pics/l_r_wert.png)  
Beispiele für L- und R-Werte  

&nbsp;

> Bestimmte Operatoren können nur auf L-Werte angewandt werden. So kann man den Inkrementoperator **++** oder den Adressoperator **&** nur auf L-Werte anwenden.  

&nbsp;

<a name="ch1-4"></a>
### 1.4 Auswertungsreihenfolge  

Wie in der Mathematik spielt es bei C eine wichtige Rolle, in welcher Reihenfolge ein Ausdruck berechnet wird.  

1. Wie in der Mathematik werden als erstes **Teilausdrücke in Klammern** ausgewertet.  
2. Dann werden **Ausdrücke mit unären Operatoren** ausgewertet.  
   Unäre Operatoren werden von rechts nach links angewendet. Dies bedeutet, dass  
      2.1 zuerst die **Postfix-Operatoren** auf ihre Operanden  
      2.2 und dann die **Präfix-Operanden** auf ihre Operanden angewendet werden  
3. Anschließend werden Teilausdrücke mit **mehrstelligen Operatoren** ausgewertet  

&nbsp;

<a name="ch1-5"></a>
### 1.5 Headers and Libraries  
Generally, a header file notifies the compiler of certain things (mostly their existence or declarations) so that the compiler can correctly build a single translation unit (such as a single C file).  

A library file is the actual executable code that does the work as specified in that header file. This is linked in by the linker to provide the actual functionality (the definitions rather than just the declarations).  

So, for example, you must have the line `#include <pthread.h>`  which tells the compiler all about the existence of the functions but doesn't actually provide the implementation of those things.  

In the Makefile, for this example, the `-lpthread` option tells the linker that it should locate a library based on the `pthread` name from which it can pull in the actual implementations, in order to form the final executable.  

Similarly, while `stdio.h` holds information about the I/O stuff, the actual code for it will be in the runtime library (though you rarely have to link that library specifically since the compiler will try to take care of it for you). Because you usually link with the compiler (i.e. the compiler invokes the linker for you), it knows that you're probably going to need the C run-time library. If you were to use the linker directly (such as by using the `ld` command), that probably wouldn't happen and you'd have to be explicit.  

&nbsp;

<u>Possibilities for including:</u>  
- Include file *xy.h* from parent directory  
`#include "../xy.h"`
- Include file *xy.h* from specified `include directories`  
  `#include <xy.h>`

With "...", the file is searched relative to the current directory, whereas with \<...\> the search only takes place in the system and specified 'include directories', which normally don't include the current directory.

&nbsp;

<a name="ch1-6"></a>
### 1.6 Memory Management - 'Heap' vs 'Stack'  

Two ways of object creation:

- via Pointer
  ```c
  Object *myObj = new Object;
  myObj->testFunc();
  ```

- via Object
  ```c
  Object myObj;
  myObj.testFunc();
  ```

Two ways of object creation are demonstrated. The main difference is the storage duration of the object. When doing `Object myObj;` within a block, the object is created with automatic storage duration, which means it will be destroyes automatically when it goes of scope. When you do `new Object;`. the object has dinamic storage duration, which means it stays alive until you explicitly `delete`. You should only use dynamic storage duration when you need it.  

The main two situations in which you might require dynamic allocation:  
1. You need the object to outlive the current scope. That specific object at that specific memory location, not a copy of it. If you are ok with copying/moving the object (most of the time should be), you should prefer an automatic object.  
2. You need  to allocate a lot of memory, which may easily fill up the stack (e.g. in case of a dynamic array).  

&nbsp;

**[-!-]** 
When you do absolutely require dynamic allocation, you should encapsulate it in a `Smart Pointer`. 'Smart Pointers' provide ownership semantics of dynamically allocated objects and provide the additional feature of automatic memory management: When the pointer is no longer in use, the memory it points to is deallocated.  
- Use `std::unique_ptr` when you don't intend to hold multiple reference to the same object. For example, use it for a pointer to memory which gets allocated on entering some scope and deallocated on exiting the scope.  
- Use `std::shared_ptr` when you do want to refer to your object from multiple places - and do not want it to be deallocated until all these references are themselves gone.  

&nbsp;  

- Comparison *Java* &harr; *C++*  
  ```java
  // Java
  Object obj1 = new Object();   // A new object is allocated by Java
  Object obj2 = new Object();   // Another new object is allocated by Java
  obj1 = obj2;  // 'obj1' now points to the object originally allocated for 'obj2'
  ```
  The object originally allocated for 'obj1' is now "dead" - nothing points to it, so it will be reclaimed by the 'Garbarge Collector'. If either 'obj1' or 'obj2' is changed, the change will be reflected to the other.  
  &nbsp;
  ```c
  // C++ - via Pointer
  Object *obj1 = new Object();   // A new object is allocated on the Heap
  Object *obj2 = new Object();   // Another new object is allocated on the Heap
  delete obj1;
  ```
  Since C++ does not have a garbage collector, the last line would cause a 'memory leak', i.e. a piece of claimed memory that the app cannot use and that we have no way to reclaim.  
  ```c
  obj1 = obj2;  // same as Java, 'obj1' points to 'obj2'
  ```
  &nbsp;
  ```c
  // C++ - via Object
  Object obj1;   // A new object is allocated on the Stack
  Object obj2;   // Another new object is allocated on the Stack
  obj1 = obj2;  // This is different !!! The CONTENTS of 'obj2' is COPIED to 'obj1'
  ```
  But the two objects are still different. Change one, the other remains unchanged. Also, the objects get automatically destroyed once the function returns.  
  &nbsp;
  > The best way to think of it is that - more or less - Java (implicitly) handles pointers to objects, while C++ may handle either pointers to objects or the objects themselves.  

&nbsp;

> **The heap is much slower than the stack, because the stack is very simple compared to the heap. Automatic storage variables (aka stack variables) have their destructors called once they go out of scope.**  

&nbsp;

- *Heap* vs *Stack*  
  &nbsp;  
  The **stack** is the memory set aside as scratch space for a thread of execution. When a function is called, a block is reserved on the top of the stack for local variables and some bookkeeping data. When that function returns, the block becomes unused and can be used the next time a function is called. The stack is always reserved in a LIFO (*last in first out*) order; the most recently reserved block is always the next block to be freed. This makes it really simple to keep track of the stack; freeing a block from the stack is nothing more than adjusting one pointer.  
  &nbsp;  
  The **heap** is memory set aside for dynamic allocation. Unlike the stack, there's no enforced pattern to the allocation and deallocation of blocks from the heap; you can allocate a block at any time and free it at any time. This makes it much more complex to keep track of which parts of the heap are allocated or freed at any given time; there are many custom heap allocators available to tune heap performance for different usage patterns.  
  &nbsp;  
  Each thread gets a **stack**, while there's typically only one **heap** for the application (although it isn't uncommon to have multiple heaps for different types of allocation).  
  - The OS allocates the stack for each system-level thread when the thread is created. Typically the OS is called by the language runtime to allocate the heap for the application.  
  - The stack is attached to a thread, so when the thread exists the stack is reclaimed. The heap is typically allocated at application startup by the runtime, and is reclaimed when the application (technically: 'process') exists.  
  - The size of the stack is set when a thread is created. The size of the heap is set on application startup, but can grow as space is needed (the allocator requests  more memory from the operating system).  


&nbsp;

<a name="ch1-7"></a>
### 1.7 Die Funktion `main`  
Es ist möglich der 'main'-Funktion eine Parameterliste zu übergeben.  
```c
// 'main' function header  
int main (int argc, char *argv[])
```

`args` - speichert die Anzahl der Parameter ('argument count')  
`argv` - speichert die Parameter an sich ('argument values')  

Es besteht also die Möglichkeit, Argumente als Parameter an unser Programm (die spätere .exe) zu übergeben, ähnlich wie bei Funktionen. Hierfür benötigt man ein erweitertes Grundgerüst ('argc' und 'argv' in main-Parameterliste).  

Nachdem man ein Programm kompiliert hat, kann man es über die Shell oder Eingabeauforderung mit Parametern starten. Folgendes Testprogramm gibt lediglich die Werte der Parameter 'argc' und 'argv' aus:  
```c
#include <stdio.h>  

int main(int argc, char* argv[]) {
  int i;
  printf("argc: %d\n", argc);
  for (i=0; i<argc; i++) {
    printf("argv[%d]: %s\n", i, argv[i]);
  }
  return 0;
}
```

In diesem Beispiel ist der Name der kompilierten Datei 'foo.exe'. ein Aufruf und die resultierende Ausgabe könnte wie folgt aussehen:  
```c
C:\> foo kurt hannes  
argc: 3
argv[0]: foo  
argv[1]: kurt  
argv[2]: hannes  
```

Der erste Wert des Parameter-Arrays 'argv' ist immer der Programmname selbst, in diesem Falle 'foo'. Dahinter folgen die wirklichen Parameter bzgl. des Programmaufrufs.

&nbsp;

<a name="ch1-8"></a>
### 1.8 Übersicht Datentypen in C  

|Type |Storage Size |Value range |  
|:---|:---:|:---:|  
|char |1 byte |-128 to 127 or 0 to 255 |  
|unsigend char |1 byte |0 to 255 |  
|signed char |1 byte |-128 to 127 |  
|int |2 or 4 bytes |-32.768 to 32.767 or -/+2.147.483.648 |  
|unsigned int |2 or 4 bytes |0 to 65.535 or 0 to 4.294.967.295 |  
|short |2 bytes |-32.768 to 32.767 |  
|unsigned short |2 bytes |0 to 65.535 |  
|long |4 bytes |-2.147.483.648 to 2.147.483.647 |  
|unsigned long |4 bytes |0 to 4.294.967.295 |  
|float |4 bytes |1.2E-38 to 3.4E+38 |  
|double |8 bytes |2.3E-308 to 1,7E+308 |  
|long double |10 bytes |3.4E-4932 to 1.1E+4932 |  

&nbsp;

**Advice on Signed/Unsigned**  

Operands with different types get converted when you do arithmetics. Everything is converted to the floatiest, longest operand, signed if possible without losing bits.  

> Avoid unnecessary complexity by minimizing your use of unsigned types. Specifically, don't use an unsigned type to represent a quantity just because it will never be negative. Use a signed type like 'int' and you won't have to worry about boundary cases in the detailed rules for promoting mixed types.  
> Only use unsigned types for bitfields or binary masks. Use casts in expressions, to make all the operands signed or unsigned, so the compiler does not have to chose the result type.

&nbsp;

<a name="ch1-9"></a>
### 1.9 Threads und Prozesse  

Both, processes and threads, are independent sequences of execution. The typical difference is that **threads (of the same process) run in a shared memory space, while processes run in separate memory space**.  

Im ersten Moment besteht kein Unterschied zwischen einem Prozess und einem Thread, denn letztendlich besteht ein Prozess mindestens aus einem Thread. Ferner endet ein Prozess, wenn sich alle Threads beenden. Somit ist der eine Prozess (dieser eine Prozess ist der erste Thread, auch *Main Thread* bzw. *Haupt-Thread* genannt) verantwortlich für die gleichzeitige Ausführung mehrerer Threads - da doch Threads auch nur innerhalb eines Prozesses ausgeführt werden. Der hauptsächliche Unterschied zwischen Threads und Prozessen besteht darin, dass Threads unabhängige Befehlsfolgen innerhalb eines Prozesses sind.  

Benefits von Threads:  
- gemeinsamer Speicherbereich aller Threads in einem Prozess (d.h. einfache Programmierung der Inter-Thread-Kommunikation)  
- Möglichkeit den einzelnen Threads Prioritäten zuzuordnen (d.h. ein Thread kann mit einer höheren Priorität laufen als ein anderer)  
- Ausnutzung mehrerer Prozessorkerne und damit Reduzierung der Gesamtrechenzeit  

Threads are not part of the C standard, so the only way to use threads is to include some library:  
- POSIX threads ('*pthreads*') in UNIX/Linux  
- *_beginthread* / *_beginthreadex* if you want to use the C runtime library (WIN32API)  
- *pthreads-win32* ('pthreads' implementation for Windows)

&nbsp;

<a name="ch1-10"></a>
### 1.10 Benutzerdefinierte Datentypen  

<a name="ch1-10-1"></a>
`typedef`  
Mit Hilfe dieses Schlüsselwortes können Sie einen Datentyp umbenennen. Dabei wird kein neuer Datentyp erzeugt, sondern lediglich ein bereits bestehender unter einem neuen Namen angesprochen. Die allgemeine Form der Anweisung lautet:  
```c  
typedef <Datentyp> <Neuer_Name>
```  

Der Datentyp muss ein in C gültiger Datentyp sin, wobei auch selbst definierte vom Typ 'struct' oder 'union' zulässig sind. Der neue Name muss in Übereinstimmung mit der Namenskonvention für Bezeichner gewählt werden.  

```c
// z.B.
typedef unsigned char UCHAR
typedef unsigned short USHORT
typedef unsigned long ULONG
typedef unsigned int UINT
```  

Wie diese Auflistung schon vermuten lässt, spricht die verbesserte Lesbarkeit des Programms für 'typedef'.  

&nbsp;

<a name="ch1-10-2"></a>
`enum`  
Aufzählungstypen sind gedacht für Integer-Variablen, die nicht jeden beliebigen Wert annehmen dürfen, sondern auf eine begrenzte Anzahl von Werten beschränkt sind. Diese Werte werden über Namen angesprochen. Die allgemeine Form einer 'enum'-Anweisung lautet:  

```c
enum <Name> {element_1, element_2, ..., element_n} <Variablenliste> 
```  

Die Angabe des Namens \<Name\> für den Aufzählungstyp kann entfallen, falls eine \<Variablenliste\> angegeben wird. Allerdings können dann später neue Variablen dieses Typs nicht mehr definiert werden. Wird ein Name angegeben, dann kann auf die Variablenliste verzichtet werden, da sich später noch beliebig viele Variablen dieses Aufzählungstyps definieren lassen. Folgende Anweisung deklariert einen Aufzählungstyp mit dem Namen 'Wochentag':  

```c
enum Wochentag {SON, MON, DIE, MIT, DON, FRE, SAM}
// SON enstpricht 0, SAM entspricht 6
```

Jedes Namenssymbol steht für einen ganzzahligen Wert, wobei jedes Namenssymbol um den Wert 1 größer ist das das vorhergehende. Anfangswert für das erste Symbol beträgt standardmäßig 0. Auch eigene Werte sind möglich:  

```c
enum Himmelsrichtung {NORD, OST=90, SUED=180, WEST=270}
```

Für eine Variable des Typs 'Himmelsrichtung' stehen genau vier Werte (von NORD bis WEST) zur Auswahl. Variablen der jeweiligen Aufzählungstypen stehen nach den beiden aufgeführten enum-Anweisungen allerdings noch nicht zur Verfügung, denn beide beschränken sich auf die Deklaration eines neuen Datentyps. Damit geben sie dem Compiler bekannt, wie der Aufzählungstyp aufgebaut ist, reservieren aber noch keinen Speicherplatz. Dazu bedarf es einer Variablendefinition. Diese kann man gleich bei der Deklaration vornehmen, indem man nach der schließenden geschweiften Klammer den Namen einer oder mehrerer Variablen angibt.  

```c
// definiert die Variable 'Heute' vom Typ 'Wochentag'
enum Wochentag Heute;
```

An die Variable 'Heute' kann jederzeit eines der 7 Elemente aus der Deklarationsliste zugewiesen werden.  

```c
// MON ist keine Zeichenkette, sondern steht für den Wert 1
Heute = MON;
```

&nbsp;

<a name="ch1-10-3"></a>
`struct`   
Wenn eine Serie zusammenhängender Daten bearbeitet werden soll, erweisen sich Arrays und Pointer als geeignet. Beide unterliegen  aber der Einschränkung, dass alle Elemente vom gleichen Datentyp sein müssen. C bietet Ihnen für diesen Zweck die Struktur, mit der Sie ein Konglomerat unterschiedlicher Datentypen zu einem Datenobjekt zusammenfassen und dabei auf einzelne Elemente zugreifen können.  

Da jedes 'struct' in ihrem Aufbau völlig einzigartig sein kann, muss der Compiler vor dem Gebrauch einer Struktur über deren Zusammensetzung aufgeklärt werden. Dies geschieht in Form einer Deklaration, die quasi eine Schablone der betreffenden Struktur zur Verfügung stellt.  

```c
struct <Name> {
  Datentyp VariablenName;
  Datentyp VariablenName;
  ...
} <Variablenliste>
```

Wie schon bei den Aufzählungstypen kann auch bei der Deklaration von Strukturen entweder der \<Name\> oder die \<Variablenliste\> fehlen. Verzichten Sie auf die Angabe des Strukturnamens, dann nehmen Sie eine sog. 'anonyme Deklaration' vor. In diesem Fall stehen nur die Variablen zur Verfügung, die Sie bei der Deklaration durch Angabe in der Variablenliste definieren.  

Erst bei der Definition einer Variablen vom Typ 'struct' reserviert der Compiler ausreichend Platz, um dann alle Elemente der Struktur unterzubringen.  

```c
// Variablen-Definition vom Typ 'adresse'
struct adresse Kunde, Lieferant;

// Zugriff auf einzelne Elemente
Lieferant.ulTel = 297225;

// Oder über Zeiger
struct adresse *pAdresse;
pAdresse = &Lieferant;
(*pAdresse).ulTel = 7460688;
```

&nbsp;

**Using struct in multiple .c/.cpp files**  
  
- Case 1: Sharing the definition of a struct  
- Case 2:Sharing a global instance of a struct  

(1) If you are trying to **share the definition of a struct** among several compilation units (.c/.cpp files), the common way is the following: Place the definition of your struct in a header file. If the struct contains any methods (i.e. it is rather a class with all member public by default in cpp), you can implement them in the belonging .c/.cpp file, or, if they are lightweight, directly within the struct (which makes them inline by default).  
```c
// myStruct.h
...
struct myStruct {
  int x;
  void f1(){...}
  void f2(){...}
}
...
```
```c
// myStruct.c/.cpp
#include "myStruct.c"

// 'Implementation of 'f2()' goes here
void myStruct::f2(){...}
...
```
You can  use your struct in as many cpp files as you like, simply `#include myStruct.h`.
&nbsp;

(2) If, on the other hand, you are trying to **share a global instance of the struct** across several compilation units, do the following:
```c
// header file 'globals.h'
typedef struct {
  ...
} node;

extern node root_node;
```
This will announce that an instance is available with *external linkage* - in other words that a variable exists but is initialized elsewhere. In C, structures have no linkage, only objects and functions do.  

Then provide an implementation/definition in a source file  
```c
// any source file
#include <globals.h>
...
node root_node;
```
Now you can include 'globals.h' in any source file where 'root_node' is accessed.  

&nbsp;

**'Struct' as function parameter**  

Es ist weit verbreitet, den Typ von Strukturen durch die Verwendung von `typedef` unter einem eigenen Namen einzuführen. Auf diese Weise entfällt die Notwendigkeit, bei der Definition von Variablen oder beim Einsatz von `sizeof` das Schlüsselwort `struct` anzugeben.  

Für die Namensvergabe mittels `typedef` besteht bei Strukturen eine Kurzform:  
```c
typedef struct {
  ...
} <struct_name>
```
Diese Deklaration hält sich erst garnicht mit der Vergabe eines Namens für die Struktur auf, sondern macht sie dank `typedef` gleich als Datentyp \<struct_name\> verfügbar.  

Beispiel:  
```c
// test.h
typedef struct {
  int aa;
  ...
} ABC;

extern ABC XYZ;

void passValue(ABC *DEF, int a);
void doSomething();
```
```c
// test.c
ABC XYZ;

void passValue(ABC *DEF, int a) {
  DEF->aa = a;
  ...
}

void doSomething() {
  ...
  ...
  passValue(&XYZ, 10);
}
```

&nbsp;

<a name="ch1-10-4"></a>
`union`  
Bei einer 'Union' handelt es sich um ein Datenobjekt, dessen Speicherplatz von mehreren Variablen verschiedenen Typs genutzt werden kann.  

Während für Variablen vom Typ der Struktur  
```c
struct conv {
  short sNumber;  
  char cByte[2];
}
```

so viel Speicherplatz angefordert wird, dass die beiden Variablen 'sNumber' und 'cByte' <u>nebeneinander</u> Platz finden, müssen sich bei der Union  

```c
union conv {
  short sNumber;
  char cByte[2];
}
```

'sNumber' und 'cByte' den <u>gleichen</u> Speicherplatz teilen. Der Speicherbedarf einer 'Union' richtet sich also nicht nach der Gesamtgröße aller Elemente, sondern nach dem Platzbedarf des größten Elementes.  

Zur Initialisierung von 'Union' darf nur **ein** Wert verwendet werden, dessen Datentyp mit jenem des ersten Elementes übereinstimmt.  

Die Eigenschaft einer 'Union' mehrere Variablen innerhalb des gleichen Speicherbereiches zu versammeln, eröffnet die Möglichkeit, diesen Speicherabschnitt unter 'verschiedenen Gesichtspunkten' zu betrachten. Z.B. können vier Byte wahlweise als float, long, oder als char-Array mit 4 Elementen betrachtet werden.

&nbsp;

<a name="ch1-11"></a>
### 1.11 Precompiled Header  

In computer programming, a *precompiled header* is a (C or C++) header file that is compiled into an intermediate form, that is <u>faster to process for the compiler</u>.  

Usage of *precompiled headers* may significantly reduce compilation time, especially when applied to large header files or header failes that include many other header files.

&nbsp;

<a name="ch1-12"></a>
### 1.12 *Header Guard* (oder 'Include Guard')  

> "*Header Guards* are little pieces of code that protect the contents of a header file from being included more than once."  

Header guards are implemented through the use of preprocessor directives. The C/C++ preprocessor directives all start with the `#` character. You are already familiar with some ('#include' / '#define'). The preprocessor performs some simple textual replacements on a file before handing it off to the compiler.  

Some of the preprocessor directives are conditional. The `#ifdef SYMBOL` directive is true when *SYMBOL* has been defined in the code seen so far. If the directive is true, then the statements that come between the `#ifdef` and `#endif` directive later on will be used in the program. If the `#ifdef` is false, then the statements from that point on will be ignored and not sent to the compiler.  

Header guards are implemented by using three preprocessor directives in a header file. Two are placed at the beginning of the file, before any pertinent code. The last is placed at the end of the file. The first header guard line is of the form  
```c
#ifndef MY_SYMBOL_H
```  
and is followed immediately by the line  
```c
#define MY_SYMBOL_H
```

The line  
```c
#endif /* MY_SYMBOL_H */
```
is placed at the end of the file.  

The symbol used is not crucial, but it must be unique. It is traditional to use all capital letters for the symblo. Only letters, numbers and the underscore character can be used in the symbols. No other punctuation is allowed. A very common symbol is to use the name of the header file, converting the `.h` suffix to a `_H`.

&nbsp;

<a name="ch1-13"></a>
### 1.13 *Calling Convention* (`__stdcall`)  
```c
#define CALLBACK __stdcall
#define WINAPI __stdcall
#define WINAPIV __cdecl
#define APIENTRY WINAPI
```
All functions in C/C++ have a particular calling convention. The point of a calling convention is to establish how data is passed between the caller and callee and who is responsible for operations such as cleaning out the call stack.  

The most popular calling conventions on windows are  
- __stdcall, Pushes parameters on the stack, in reverse order (right to left); Callee cleans the call stack
- __cdecl, Pushes parameters on the stack, in reverse order (right to left); Caller cleans the call stack
- __clrcall, Load parameters onto CLR expression stack in order (left to right)
- __fastcall, Stored in registers, then pushed on stack
- __thiscall, Pushed on stack; this pointer stored in ECX

&nbsp;

<a name="ch1-14"></a>
### 1.14 Namespaces  

In C++, namespaces provide a method for preventing name conflicts in large projects.

Symbols declared inside a namespace block are placed in a named scope that prevents them from being mistaken for identically-named symbols in other scopes. Multiple namespace blocks with the same name are allowed. All declarations within those blocks are declared in the named scope.  

1) Named namespace definition for the namespace ns_name:
   `namespace ns_name { declarations }`  
2) Namespace names (along with class names) can appear on the left hand side of the scope resolution operator, as part of qualified name lookup:
   `ns_name::name`  
3) using-directive: From the point of view of unqualified name lookup of any name after a using-directive and until the end of the scope in which it appears, every name from ns_name is visible as if it were declared in the nearest enclosing namespace which contains both the using-directive and ns_name:  
   ``using ns_name::name;``  

&nbsp;

Examples:

```c
namespace Q {
  namespace V { // V is a member of Q, and is fully defined within Q
// namespace Q::V { // C++17 alternative to the above two lines
    class C { void m(); }; // C is a member of V and is fully defined within V
                           // C::m is only declared
    void f(); // f is a member of V, but is only declared here
  }
  void V::f() // definition of V's member f outside of V
              // f's enclosing namespaces are still the global namespace, Q, and Q::V
  {
      extern void h(); // This declares ::Q::V::h
  }
  void V::C::m() // definition of V::C::m outside of the namespace (and the class body)
                 // enclosing namespaces are the global namespace, Q, and Q::V
  {
  }
}
```

- **(!) Define alias for namespace** (e.g. in *defs.h*)  (for use in multiple files):
  ```c
  ...
  #define APPL_BEGIN_NAMESPACE namespace appl {
  #define APPL_END_NAMESPACE }
  ...
  ```
&nbsp;

<a name="ch1-15"></a>
### 1.15 `extern c` in C++  

[&rarr;&nbsp;&nbsp; How to mix C and C++](https://isocpp.org/wiki/faq/mixing-c-and-cpp)  

&nbsp;

`extern "C"` makes a function-name in C++ have C linkage (compiler does not mangle the name) so that client C code can link to (use) your function using a C compatible header file that contains just the declaration of your function. Your function definition is contained in a binary format (that was compiled by your C++ compiler) that the client C linker will then link to using the C name.  

Since C++ has overloading of function names and C does not, the C++ compiler cannot just use the function name as a unique id to link to, so it mangles the name by adding information about the arguments. A C compiler does not need to mangle the name since you can not overload function names in C. When you state that a function has `extern "C"` linkage in C++, the C++ compiler does not add argument/parameter type information to the name used for linkage.  

Just so you know, you can specify `extern "C"` linkage to each individual declaration/definition explicitly or use a block to group a sequence of declarations/definitions to have a certain linkage:  
```c
extern "C" void foo(int);
extern "C"
{
   void g(char);
   int i;
}
```
&nbsp;

Furthermore  
- `extern "C"` is a linkage-specification
- Every compiler is required to provide "C" linkage
- A linkage specification shall occur only in namespace scope
- Only function names and variable names with external linkage have a language linkage
- Two function types with distinct language linkages are distinct types even if otherwise identical
- Linkage specs nest, inner one determines the final linkage
- `extern "C"` is ignored for class members
- At most one function with a particular name can have "C" linkage (regardless of namespace)
-`static` inside `extern "C"` is valid; an entity so declared has internal linkage, and so does not have a language linkage
- Linkage from C++ to objects defined in other languages and to objects defined in C++ from other languages is implementation-defined and language-dependent. Only where the object layout strategies of two language implementations are similar enough can such linkage be achieved  

> C compiler does not use mangling which c++'s does. So if you want call a c interface from a c++ program, you have to clearly declared that the c interface as `"extern c"`.

&nbsp;

In C code, one often sees this:  
```c
#ifdef __cplusplus
extern "C" {
#endif

// all of your legacy C code here

#ifdef __cplusplus
}
#endif
```
What this accomplishes is that it allows you to use that C header file with your C++ code, because the macro `"__cplusplus"` will be defined. But you can also still use it with your legacy C code, where the macro is NOT defined, so it won't see the uniquely C++ construct.

&nbsp;

<a name="ch1-16"></a>
### 1.16 *Forward Declaration* in C++  

Two ways of including a class:
1. including header file: `#include A.h`
2. use *forward declaration*: `class A;`  

When you forward declare a type, all the compiler knows is that this type exists. It knows nothing about its size, members or methods. This is why it's called an **incomplete type**. Therefore you cannot use the type to declare a member or a base class since the compiler would need to know the layout of the type.  

a) What you <u>can</u> do with an incomplete type  
   - Declare a member to be a pointer or a reference  
     `class Foo { A *pt; A &pt; }`  
   - Declare functions or methods which accept/return incomplete types  
     `void f1(A); a f2();`  
   - Define functions or methods which accept/return pointers/references to the incomplete type  
     `void f3(A*, A&) {...}; A& f4() {...}; A* f5() {...};`  

b) What you <u>can't</u> do with an incomplete type  
   - Use it as a base class  
     `class Foo: A {...}     // compiler error`
   - Use it to declare a member  
     `class Foo { A m; }     // compiler error`
   - Define functions or methods using this type  
     `void f1(A a) {...}     // compiler error`
     `A f2() {...}           // compiler error`
   - Use its methods or fields  

&nbsp;

Advantages of 'forward declaration'  
  - Reduced compile time  
  - No namespace pollute  
  - (In some cases) may reduce the size of your generated binaries  
  - Recompilation time can be reduced  
  - Avoiding potential clash of preprocessor names  

&nbsp;

<a name="ch1-17"></a>
### 1.17 'Function Prototype' and Definition in C  

If you have a function that is used in only one .c file, you can put its declaration and definition in the same .c file (and you should probably define it as `static`). In fact, if the definition appears before any calls, you can omit the separate declaration - the definition itself acts as a declaration.  

&nbsp;

<a name="ch1-18"></a>
### 1.18 Präprozessor in C/C++  

Der Präprozessor gehört zum Compiler und verändert den Quelltext nach Anweisungen, welche im Quelltext (oder Makefile) festgelegt werden. Wie das Stichwort 'Prä' verrät, wird der Präprozessor <u>vor</u> der eigentlichen Kompilierung ausgeführt. D.h. der Präprozessor verändert vor dem Kompilieren den Quelltext, danach wird der neue Quelltext kompiliert.  

Die häufigste Nutzung des Präprozessors besteht im Einschleusen anderer Dateiinhalte:  
```c
#include <stdio.h>

int main(void) {
  printf("Hello World!");
  return 0;
}
```

Der Präprozessor ersetzt die Zeile `#include <stdio.h>` mit dem Inhalt der Header-Datei 'stdio.h' in der unter anderem die Funktion 'printf()' deklariert wird.  

Die Anweisungen'#if', '#ifdef', '#ifndef', '#else' und '#endif' werden für bedingte Ersetzungen des C-Präprozessors verwendet. z.B.  
```c
#ifdef WIN32
  #include <window.h>
#else
  #include <unistd.h>
#endif
```
In diesem Beispiel prüft der C-Präprozessor, ob ihm ein Makro namens 'WIN32' bekannt ist. Ist das der Fall, wird der Dateiinhalt von \<windows.h\> eingeschleust, ansonsten der von \<unistd.h\>.

- `CFLAGS`  
  'CFLAGS' are the name of environment variables or of Makefile variables that can be set to **specify additional switches to be passed to a compiler** in the process of building computer software. These variables are usually set inside a Makefile and are **appended to the command line** when the compiler is invoked.  
  &nbsp;  
  So the line in the Makefile 
  ```c
  DEF_CFLAGS += -DWITH_FLEXRAY
  ```
  is the equivalent ot putting
  ```c
  #define WITH_FLEXRAY 1
  ```
  at the top of all .c and .h files in your project.  
  Inside your code you can then tell the preprocessor (or precompiler) which code to forward to the compiler  
  ```c
  #ifdef (WITH_FLEXRAY)
    ...
  #endif
  ```

&nbsp;

<a name="ch1-19"></a>
### 1.19 'Name Mangling' (or 'Name decoration')  

In compiler construction 'name mangling' is a technique used to solve various problems caused by the need to resolve various names for programming entities in many modern programming languages. It provides a way of encoding  additional information in the name of a function, structure, class or another datatype in order to pass more semantic information from the compilers to linkers.  

Any object code produced by compilers is usually linked with other pieces of object code (produced by the same or another compiler) by a type of program called a linker. The linker needs a great deal of information on each program entity. For example, to correctly link a function it needs its name, the number of arguments anf their typed, and so on.  

C++ compilers are the most widespread users of 'name mangling'. The first C++ compilers were implemented as translators to C source code, which would be compiled by a C compiler to object data. Because of this, symbol names had to conform to C identifier rules. C++ has also complex language features, such as classes, templates, namespaces and operator overloading, that alter the meaning of specific symbols based on context or usage. Meta-data about these features can be disambiguated by mangling (or decorating) the name of a symbol.  

```c
int f(void) { return 1; }
int f(int) { return 0; }
void g(void) { int i = f(); }
```
The C++ compiler will encode the type information in the symbol name, the result being sth like:
```c
int __f_v(void) { return 1; }
int __f_i(int) { return 0; }
void __g_v(void) { int i = __f_i(); }
```
Even though its name is unique, 'g()' is still mangled: name mangling applies to <u>all</u> symbols.

&nbsp;

**`nm` command (Unix)**  

The `nm` command ships with a number of later versions of Unix and similar operating systems. `nm` is used to examine binary files (including libraries, compiled object modules, shared object files and standalone executables) and to display the contents of those files or meta-information stored in them, specifically the `symbol table`.  

`nm` is used as an aid for debugging, to help resolve problems arising from name conflicts and C++ 'name mangling'.  

```c
// Example:
// File name 'test.c'

int global_var;
int global_var_init = 26;
static int static_var;
static int static_var_init = 25;

static int static_function() {...}
int global_function2() {int x; int y;}
int global_function(int p) {static int local_stat_vars;}

#ifdef __cplusplus
  extern "C"
#endif

void non_mangled_functions() {...}
int main (void) {global_var = 1;static_var = 2;}
```

(a) Compiled with the gcc C compiler, the output of `nm test.o` is
```
0 0 0 0 0 0 0 a    T    global_function
0 0 0 0 0 0 2 5    T    global_function2
0 0 0 0 0 0 0 4    C    global_var
0 0 0 0 0 0 0 0    D    global_var_init
0 0 0 0 0 0 0 4    b    local_static_var.1255
0 0 0 0 0 0 3 6    T    main
0 0 0 0 0 0 3 6    T    non_mangled_function
0 0 0 0 0 0 0 0    t    static_function
0 0 0 0 0 0 0 6    b    static_var
0 0 0 0 0 0 0 4    d    static_var_init
```

(b) When the C++ compiler is used, the output of `nm test.o` is
```
0 0 0 0 0 0 0 a    T    -z15global_functioni
0 0 0 0 0 0 2 5    T    -z16global_function2v
0 0 0 0 0 0 0 4    b    -ZL10static_var
0 0 0 0 0 0 0 0    t    -ZL15static_functionv
0 0 0 0 0 0 0 4    d    -ZL15static_var_init
0 0 0 0 0 0 0 8    b    -ZZ15global_functionE16Loc...
                   U    _gxx_personality_v0
0 0 0 0 0 0 0 0    B    global_var
0 0 0 0 0 0 0 0    D    global_var_init
0 0 0 0 0 0 3 6    T    main
0 0 0 0 0 0 3 6    T    non_mangled_function
```

The difference between the outputs also show an example of solving the name mangling problem by using `extern "c"` in C++ code.

Tag meaning:  
`"T"/"t"`: The symbol is in the text (code) section  
`"D"/"d"`: The symbol is in the initialized data section  
`"B"/"b"`: The symbol is in the uninitialized data section  
`"U"`: The symbol is undefined  

> To write output of `nm` command to file use command: `nm <binary> >& link.txt`  

&nbsp;

**`dumpbin` command (Windows)**  

The Microsoft COFF Binary File Dumper displays information about 'Common Object File Format' binary files. You can use `DUMPBIN` to examine COFF object files, standard libraries of COFF objects, executable files and dynamic-linked libraries (DLL's).  

**[-!-]** You can start this tool only from the Visual Studio command prompt. You cannot start it from a system command prompt or from File Explorer.  

To use `DUMPBIN`, use the following syntax:
```c
DUMPBIN [options] files ...
```

&nbsp;

&nbsp;


# Arrays  

<a name="ch2-1"></a>
### 2.1 Basics  

In C gibt es im Gegensatz zu anderen Sprachen **kein Schlüsselwort array**. Der C-Compiler erkennt ein Array an den eckigen Klammern, die bei der Definition die Anzahl der Elemente enthalten. Die **Anzahl der Elemente** muss immer eine positive ganze Zahl sein. Sie kann gegeben sein durch eine Konstante oder einen konstanten Ausdruck, **nicht aber durch eine Variable**. Dies bedeutet, dass die Größe nicht dynamisch zugeordnet werden kann. Dennoch können Arrays mit einer zur Laufzeit berechneten Größe mit Hilfe der Funktion `malloc()` oder `calloc()` konstruiert werden.  
&nbsp;

Ein eindimensionaler Vektor (eindimensionales Array) wird folgendermaßen definiert:  
```c
int alpha[5];     //Definition des Arrays alpha mit Platz für 5 int-Zahlen
```

Eine einfache Möglichkeit, einen Pointer auf ein Arrayelement zeigen zu lassen, besteht darin, auf der rechten Seite des Zuweisungsoperators den **Adressoperator &** wie folgt zu verwenden:  
```c
int * pointer;          //Definition des Pointers pointer  
pointer = &alpha[i-1]   // Pointer zeigt auf das i-te Arrayelement
```

Hat *i* den Wert 1, so zeigt der Pointer *pointer* auf das 1. Element des Arrays. Dieses hat den Index 0.  

> Der Name eines Arrays kann als konstanter Zeiger auf das erste Element des Arrays verwendet werden.  

&nbsp;

![03](../assets/pics/pointer_array.png)  
Pointer auf ein Array  

&nbsp;

Damit gibt es für das erste Element zwei gleichwertige Schreibweisen:
  - *alpha[0]*  
  - oder, mit Verwendung des Dereferenzierungsoperators, \*alpha  

Der Compiler rechnet intern nicht mit Indizes. Erhält er eine Array-Komponente, so rechnet er den Index sofort in einen Pointer um.  
&nbsp;

> Eine tückische Besonderheit von Arrays in C ist, dass beim Überschreiten des zulässigen Indexbereiches kein Kompilier- bzw. Laufzeitfehler erzeugt wird. So würde bei einem Array `int alpha[5]` die Anweisung `alpha[5] = 6` einfach die Speicherzelle direkt nach `alpha[4]` mit dem Wert 6 überschreiben.  


> Auf jeden Fall sollte man es sich bei Arrays zur Gewohnheit machen, immer mit symbolischen Konstanten wie z.B. `#define MAX 40` und nie mit literalen Konstanten wie z.B. `int fahrenheit [40]` zu arbeiten. Soll nämlich der Wert in einer nächsten Version des Programms bis 100 Grad Celsius betragen, so müsste man doch  an vielen Stellen (z.B. in den Eingabeauforderungen und in den Kommentaren) Änderungen vornehmen, von denen leider gerne welche vergessen werden.  

&nbsp;

<a name="ch2-2"></a>
### 2.2 Übergabe von Arrays  

Bei der Übergabe eines Arrays an eine Funktion wird als aktueller Parameter der Arrayname übergeben. Der Arrayname stellt dabei einen Pointer auf das erste Element des Arrays dar.  

> Der formale Parameter für die Übergabe eines eindimensionalen Arrays kann ein offenes Array sein - oder wegen der Pointereigenschaft des Arraynamens - auch ein Pointer auf den Komponententyp des Arrays.  

```c
#include <stdio.h>
#define GROESSE 3

void init (int *, int);
void ausgabe(int[], int);

int main (void)
{
  int i [GROESSE];
  init (i, GROESSE);
  ausgabe (i, GROESSE);
  return 0;  
}

void init (int *alpha, int dim)   // hier ist alpha ein Pointer
{
  ...
}

void ausgabe (int alpha[], int dim)   // hier ist alpha vom Typ eines offenen Arraynamens
{
  ...
}
```

&nbsp;

<a name="ch2-3"></a>
### 2.3 Übergabe von Zeichenketten

Da Zeichenketten vom Compiler intern als *char*-Arrays gespeichert werden, ist die Übergabe von Zeichenketten identisch mit der Übergabe von *char*-Arrays. Der formale Parameter einer Funktion, die eine Zeichenkette übergeben bekommt, kann vom Typ ``char*`` oder ``char[]`` sein.  

&nbsp;

&nbsp;


# Pointer  

<a name="ch3-1"></a>
### 3.1 Referencing and Dereferencing

`Referencing` means taking the address of an existing variable (using `&`) to set a pointer variable. In order to be valid, a pointer has to be set to the address of a variable of the same type as the pointer, without the asterisk (`*`).  
```c
int c1;  
int *p1;
c1 = 5;  
p1 = &c1;   // "p1 reference c1"
```

> `&` is the reference operator and can be read as `address of`.  

&nbsp;

``Dereferencing`` a pointer means using the `*` operator (*asterisk* character) to access the value stored at a pointer.  The value stored at the address of the pointer must be a vlue of the same type of variable the pointer 'points' to, but there is no guarantee this is the case unless the pointer was set correctly. The type of variable the pointer points to is the type less the outermost asterisk.  
```c
int n1;
n1 = *p1;  // reading access, i.e. n1 is now 5
*p1 = 7;   // writing access, i.e. c1 is now 7
```

> `*` is the dereference operator and can be read as `value pointed by`.

&nbsp;

<a name="ch3-2"></a>
### 3.2 Addition und Subtraktion  

Wird ein Pointer vom Typ ``int *`` um 1 erhöht, so zeigt er um ein int-Objekt weiter. Wird ein Pointer  vom Typ `float *` um 1 erhöht, so zeigt er um ein float-Objekt weiter. Die Erhöhung um 1 bedeutet, dass der Pointer immer um ein Speicherobjekt vom Typ, auf den der Pointer zeigt, weiterläuft.  

&nbsp;

![04](../assets/pics/var_alpha.png)  

&nbsp;

Nach der Variablen *alpha* in obigem Bild können Variablen eines anderen Typs liegen. Der Pointer lässt sich nicht beirren, er läuft im *int*-Raster weiter.

&nbsp;

<a name="ch3-3"></a>
### 3.3 Call-by-Value  

In vielen Programmiersprachen werden im Normalfall Parameter an Funktionen mithilfe einer Kopie übergeben. Das wird als **call-by-value** bezeichnet. Das bedeutet, dass innerhalb der aufgerufenen Funktion mit der Kopie gearbeitet wird und sich Änderungen nicht auf den ursprünglichen Wert auswirken.

&nbsp;

<a name="ch3-4"></a>
### 3.4 Call-by-Reference

Manche Programmiersprachen wie z.B. C++ kennen außer der **call-by-value** Schnittstelle auch eine **call-by-reference** Schnittstelle. Eine call-by-reference Schnittstelle ermöglicht es, über Übergabeparameter nicht nur Werte in eine Funktion hinein, sondern auch aus ihr heraus zu bringen.  

&nbsp;

**[C]**

In C ist eine call-by-reference Schnittstelle als Sprachmittel nicht vorgesehen. Man kann das Verhalten einer call-by-reference Schnittstelle, nämlich Werte über die Parameterliste an den Aufrufer zu übergeben, auch mit der call-by-value Schnittstelle erreichen, indem man einen Pointer auf den aktuellen Parameter mit call-by-value übergibt.  

```c
#include <stdio.c>

void init (int * alpha)
{
  * alpha = 10;
}

int main (void)
{
  int a;
  init (&a);
  printf ("Der Wert von a ist %d", a);
  return 0;
}
```

Ausgabe: *Der Wert von a ist 10*

> Beim Aufruf von `init (&a)` wird die lokale Variable `alpha` angelegt. Sie wird mit dem Wert des aktuellen Parameters initialisiert, also mit der Adresse von a. Man kann sich das als Kopiervorgang vorstellen: `int * alpha = &a`   

&nbsp;

**[C++]**

Die **call-by-reference** Methode zum Übergeben von Argumenten an eine Funktion kopiert die Referenz eines Arguments in den formalen Parameter. Innerhalb der Funktion wird die Referenz verwendet, um auf das tatsächliche Argument zuzugreifen, das im Aufruf verwendet wird. Dies bedeutet, dass Änderungen am Parameter das übergebene Argument beeinflussen.

Um den Wert als Referenz zu übergeben, wird die Argumentreferenz wie bei jedem anderen Wert an die Funktionen übergeben. Dementsprechend müssen Sie die Funktionsparameter wie in der folgenden Funktion *swap ()* als Referenztypen deklarieren, die die Werte der beiden ganzzahligen Variablen austauscht, auf die ihre Argumente verweisen.

````c
void swap (int &x, int &y) {
   int temp;
   temp = x;
   x = y;    
   y = temp;

   return;
}

int main () {
   int a = 100;
   int b = 200;

   swap(a, b);

   return 0;
}
````

&nbsp;

<a name="ch3-5"></a>
### 3.5 Pointer auf Pointer  

|||
|:---:|:---:|
|\*ptr | Pointer zeigt auf eine Speicherstelle|
|\*\*ptr|  Pointer zeigt auf einen Pointer|
|||

Man hat einen Zeiger der auf einen Zeiger zeigt, der auf eine Variable zeigt und auf diese Variable zugreifen kann. Es wird dabei von *mehrfacher Indirektion* gesprochen. Am häufigsten werden Zeiger im Zusammenhang mit Arrays von Zeigern eingesetzt.  

```c
int matrix [zeile][spalte]
```

```c
int **matrix;
matrix = malloc(zeile * sizeof(int));        //Reservierung für Speicher für die Zeile

for (i=0; y<zeile; i++) {                    
  matrix[i] = malloc(spalte * sizeof(int));  //Reservierung für Speicher für die Spalte
  if (NULL == matrix[i]) {
    printf("Kein Speicher mehr!");
  }
}
```

![04](../assets/pics/ptr_to_ptr.png)  

&nbsp;

- Äquivalenz zwischen Zeigern und mehrdimensionalen Arrays:

|Zugriff auf|Möglichkeit 1|Möglichkeit 2|Möglichkeit 3|
|:---:|:---:|:---:|:---:|
|1.Zeile, 1.Spalte|\*\*matrix|\*matrix[0]|matrix[0][0]|
|i.Zeile, 1.Spalte|\*\*(matrix+i)|\*matrix[i]|matrix[i][0]|
|1.Zeile, i.Spalte|\*(*matrix+i)|\*matrix[0]+i|matrix[0][i]|
|i.Zeile, j.Spalte|\*(\*(matrix+i)+j)|\*matrix[i]+j|matrix[i][j]|  

Wie im Falle der eindimensionalen Arrays gilt auch für die mehrdimensionalen Arrays, dass der Name des Arrays auf das erste Element des Arrays verweist. Für unser obiges Beispiel bedeutet dies, dass *matrx* ein Zeiger auf das erste Element des als *int matrix[4][3]* deklarierten Arrays ist. Was aber genau ist das erste Element von *matrix*? Es ist nicht die int-Variable *matrix[0][0]*! Denken Sie daran, dass *matrix* ein Array von Arrays ist. Das erste Element ist daher *matrix[0]* - ein Array von drei int-Variablen (und eines der vier untergeordneten Arrays aus *matrix*).  

Wenn aber *matrix[0]* ein Array ist, stellt sich die Frage, ob *matrix[0]* selbst wieder auf etwas verweist. Und tatsächlich, *matrix[0]* zeigt auf das erste Element *matrix[0][0]*, d.h. es ist ein Zeiger! Denken Sie daran, dass der Name eines Arrays ohne Klammern ein Zeiger auf das erste Element darstellt. Der Ausdruck *matrix[0]* ist der Name des Arrays *matrix[0][0]* ohne das letzte Klammernpaar und damit ein Zeiger.  

Folgende Regel gilt für n-dimensionale Arrays:
- Der Array-Name gefolgt von n Klammernpaaren (wobei jedes Paar einen passenden Index einschließt) wird zu Array-Daten (genauer gesagt, zu den Daten aus dem spez. Array-Element) ausgewertet.
- Der Array-Name gefolgt von weniger als n Klammernpaaren wird zu einem Zeiger auf ein Array-Element ausgewertet.

&nbsp;

<a name="ch3-6"></a>
### 3.6 Pointer auf Funktionen  

Syntax for creating a non-const function pointer:  
```c
int (*fcnPtr) (int,int);
```

`fcnPtr` is a pointer to a function that has two 'int'-parameters and returns an integer. 'fcnPtr' can point to any function that matches this type.  

Function pointers can be initialized with a function:  
```c
fcnPtr = foo;       // 'foo()' is a function defined before
```

> Common mistake is 'fcnPtr = foo()'. This would assign the return value from a call to function 'foo()'.

Note that the type (parameters and return type) of the function pointer must match the type of the function.  

&nbsp;

**`typedefs` for pointers to functions**  

The syntax for pointers to functions is ugly. 'Typedefs' can be used to make pointers to functions look more like regular variables:  
```c
typedef bool (validateFcn)(int,int);
```
This defines a typedef called 'validateFcn' that is a pointer to a function that takes two int's and returns a bool.  

Now instead of doing this:  
```c
bool validate (int x, int y, bool (*fcnPtr)(int,int));
```
you can do this:
```c
bool validate (int x, int y, validateFcn pfcn);
```


&nbsp;  

&nbsp;


# Pointer und Arrays  

<a name="ch4-1"></a>
### 4.1 Vergleich von char-Arrays und Pointern auf Zeichenketten

Prinzipiell hat man zur Speicherung von konstanten Zeichenketten zwei Möglichkeiten. Zum einen kann man ein *char*-Array definieren und dort die konstante Zeichenkette ablegen wie im folgenden Beispiel:  
```c
char buffer [] = "hello";
```

Zum anderen kann man die Speicherung der konstanten Zeichenkette, die ja eine Konstante darstellt, dem Compiler überlassen und sich nur durch den Rückgabewert der Zeichenkette einen Pointer auf das erste Element der Zeichenkette geben lassen, z.B. durch  
```c
char *pointer = "hello";
```

Hier wird der Pointer auf das 'h' von "hello" dem Pointer *pointer* zugewiesen. An dieser Operation sind nur Pointer beteiligt.  

Eine Stringvariable kann also durch die Pointernotation `char *pointer` oder als offenes Array `char buffer[]` bzew. als Array mit ausreichend festgelegter Größe definiert werden.  

Im Falle der Pointernotation zeigt der Pointer *pointer* auf eine konstante Zeichenkette, einen R-Wert.  
Die Komponenten des Arrays sind dagegen L-Werte! Im Falle des Arrays ist es damit möglich, Elemente des Arrays neu mit Werten zu belegen, z.B. durch  
```c
buffer [1] = 'a';
```
Dann lautet der gespeicherte String "hallo". Jedoch ist es nicht möglich, den Pointer *buffer*, der ein konstanter Pointer auf das erste Element des Arrays ist, woanders hinzeigen zu lassen.  

Im Falle der Pointernotation ist eine Änderung der konstanten Zeichenkette nicht vorgesehen, d.h. nicht erlaubt. Wie der Name schon sagt, soll ein konstante Zeichenkette ja konstant sein. Dafür hat man im Falle der Pointernotation die Freiheit, seinen Pointer ganz woandershin zeigen zu lassen.  

> Bei einem *char*-Array *buffer* kann der in ihm  gespeicherte String verändert werden. *buffer* ist ein konstanter Pointer auf das erste Element des Arrays und kann auf keine andere Adresse zeigen.  

> Zeigt eine Stringvariable  vom Typ char* auf eine konstante Zeichenkette, so führt der Compiler  die Speicherung der Zeichenkette selbst durch. Die Zeichenkette kann nicht verändert werden aber die Zeigervariable vom Typ char* kann eine neue Adresse zugewiesen werden.  

&nbsp;

<a name="ch4-2"></a>
### 4.2 Das Schlüsselwort `const` bei Pointern und Arrays  

Die mit *const* definierten Variablen besitzen - genau wie gewöhnliche Variablen - einen Wert, einen Typ, einen Namen und auch eine Adresse. Sie liegen also im adressierbaren Speicherbereich. Als Konstanten dürfen sie natürlich nicht auf der linken Seite der Zuweisung stehen.  

Die Formulierung mit *const* hat gegenüber der Formulierung mit *#define* unter anderem den Vorteil, auch auf zusammengesetzte Datentypen anwendbar zu sein. So bedeutet  
```c
const int feld [] = {1, 2, 3};
```

dass alle Feldelemente *feld[0]*, *feld[1]* und *feld[2]* Konstanten sind.  

Angenommen, ein *char*-Array sei definiert durch  
```c
char blick [] = "Er will es blicken";
```

Dann bedeutet  
```c
const char * text = blick;
```

nicht, dass der Pointer konstant ist, sondern dass der Pointer auf eine konstante Zeichenkette zeigt.   
```c
text[1] = 's';                          // Fehler! Nicht möglich.
text = "Jetzt blicke auch ich durch";   // Ist hier möglich!
```

Soll ein konstante Pointer eingeführt werden, so muss *const* vor dem Pointernamen stehen:
```c
char lili [] = "Ich liebe Lili";
char * const hugo = lili;

hugo[13] = 'o';             // Ist jetzt möglich!
hugo = "Ich liebe Susi";    // Fehler! Nicht mehr möglich.
```

Beim folgenden Beispiel bleibt *hugo* stets unzertrennlich mit *lili* verbunden, da zum einen der Pointer *hugo* konstant ist und auch die Zeichenkette als Konstante geschützt ist.  
```c
const char * const hugo = lili;
```

&nbsp;  

&nbsp;


# Programmsyntax und -semantik

<a name="ch5-1"></a>
### 5.1 Der Bedingungsoperator `A ? B : C`
Eine echte Rarität  in der Programmiersprache C ist der Bedingungsoperator. Er ist  nämlich der einzige Operator, der drei Operanden verarbeitet. In einem **bedingten Ausdruck**  ``A ? B : C`` wird zuerst der Ausdruck A ausgewertet. Ist der Rückgabewert von Ausdruck A ungleich 0, also wahr, so wird der Ausdruck B ausgewertet. Das Ergebnis von B ist dann der Rückgabewert des Bedingungsoperators. Ist jedoch der Ausdruck von A gleich 0, also falsch, so wird der Ausdruck C ausgewertet.  

````c  
1 == 1 ? 0 : 1      /* Rückgabewert: 0 */
0 ? 0 : 1           /* Rückgabewert: 1 */
````  

Der Ausdruck ist also gleichbedeutend mit
````c  
if (A) return B;
else return C;
````  

&nbsp;  

<a name="ch5-2"></a>
### 5.2 `switch - case`
[...] Besonders schön lesbar wird der Code, wenn man die ganzzahligen Konstanten im *switch* durch symbolische Konstanten ersetzt, deren Bedeutung dem Leser sofort klar ist. Das Definieren der symbolischen Konstanten kann durch *#define* oder noch besser durch *enum* realisiert werden.  

```c
#include <stdio.h>

int main (void)
{
  enum color {RED, GREEN, BLUE};      // (1)
  enum color col = GREEN;             // (2)
  switch (col)
  {
    case RED:
      ...
    case GREEN:
      ...
    case BLUE:
      ...
    default:
      ...
  }  
}
```

Das Programm nutzt zur Aufzählung von Konstanten den Datentyp *enum color*. Bei *(1)* werden den Konstanten *RED, GREEN* und *BLUE* die Integerwerte 0, 1 und 2 zugewiesen. Nun wird bei *(2)* eine Variable  *col* vom Typ *enum color* angelegt und der Wert *GREEN* zugewiesen. Ausgeführt werden in der darauf folgenden switch-Anweisung die Anweisung bei *case: GREEN*.  

&nbsp;  

<a name="ch5-3"></a>
### 5.3 Das Schlüsselwort ``extern``  

In C gibt es die so genannte `One definition rule`. Sie besagt, dass jedes Teil, egal ob Variable oder Funktion nur ein einziges Mal definiert werden darf. Es darf aber beliebig viele Deklarationen darauf geben, solange nur alle Deklarationen mit der Definition in den Datentypen übereinstimmen.  

Man nutzt das ganze dann so:  
In <u>einer</u> \*.c Datei wird eine Variable definiert  
```c
//globals.c  
int var_test = 100;
```
und beliebig viele andere \*.c Dateien können sich auf diese Variable beziehen.  
Dafür schreibt man, passenderweise (hier in eine Datei 'globals.h'):  
```c
//globals.h  
extern int var_test;
```
Die ist dann in jedem Sourcefile (\*.c) mit `#include globals.h` einzubinden, in dem auf die Variable 'var_test' zugegriffen werden soll.  

Am besten fasst man die Definitionen von globalen Variablen in einer zentralen C-Datei zusammen (relativ zum Programm oder Modul) und verwendet externe Deklarationen in Headerdateien, die dann mit '#include' eingebunden werden, wo immer man die Deklarationen benötigt.  

&nbsp;  

**'extern' bei structs**  
In C, structures have no linkage, only objects and functions do. So you can write this:  
```c
// header file 'globals.h'  
typedef struct
{
  ...  
} node;

extern node root_node;
```

Then provide an implementation/definition in one source file   
```c
// any source file  
#include <globals.h>

node root_node;
```
Now you can include 'globals.h' in any source file where 'root_node' is needed.  

&nbsp;  

<a name="ch5-4"></a>
### 5.4 Das Schlüsselwort ``static``  

Das Schlüsselwort 'static' hat in C eine Doppelbedeutung.  

Im <u>Kontext einer Variablendeklaration</u> innerhalb einer Funktion sagt dieses Schlüsselwort, dass diese **Variable auf einer festen Speicheradresse gespeichert wird**. Daraus ergibt sich die Möglichkeit, dass eine Funktion, die mit 'static'-Variablen arbeitet, beim nächsten Durchlauf die informationen erneut nutzt, die in der Variable gespeichert wurden (wie in einem Gedächtnis).  

Auch <u>vor Funktionen sowie Variablen außerhalb von Funktionen</u> kann das Schlüsselwort 'static' stehen. Das bedeutet, dass auf die Funktion/Variable **nur in der Datei in der sie steht zugegriffen werden kann**.  

In C functions are global by default. The 'static' keyword before a function makes it static.  
Access to static functions is restricted to the file where they are declared.Therefore, when we want to restrict access to functions, we make them static. As a consequence, usually there is no declaration in the header file anymore but in the .c file only.  
```c
static int fun(void);
...
static int fun(void)
{
    ...
}
```
Making functions 'static' can also confer performance benefits in the presence of compiler optimizations. Because a static function cannot be called from anywhere outside of the current translation unit, the compiler controls all the call points to it.  

When you declare (and define) a function as 'static' in the header file, each translation unit that includes that header file gets its own internal copy of the function. Even though these functions look absolutely the same, they are still separate, completely independent functions. The fact that they have the same name and consist of the same code means nothing to the compiler.  

`'Functions defined but not used'` warning is only issued for functions with internal linkage, i.e. functions that are declared as 'ststic'. If you don't reference these functions in their translation unit, these functions are known to be unused and the warning is generated.

&nbsp;

**'static' bei Klassenmembern [C++]**  
In Sprachen mit Klassen kann es Klassenfunktionen geben, die etwas mit der Klasse zu tun haben, aber keinerlei Daten von Instanzen dieser Klasse benötigen. Auch kann es Klassen und Variablen geben, bei denen es aus technischen Gründen nicht sinnvoll ist, mehr als eine Instanz anzulegen.  
Zu diesem Zweck können Deklarationen von Membervariablen und -funktionen mit dem Schlüsselwort 'static' versehen werden.  

Statische Variablen und Methoden werden aufgrund ihres Zweckes ohne Klasseninstanz aufgerufen, so dass häufig auch keine Instanz zur Verfügung steht, über die man die Methode  aufrufen könnte. Um dennoch auf sie zugreifen zu können, ruft man die Methode über den Namen der Klasse auf:  
```c
<Klassenname>::<Methode> (<Argumente>);
```

&nbsp;  

<a name="ch5-5"></a>
### 5.5 ``printf`` Formatierungszeichen  

```c
printf ("<text> %<format>\n", <Wert>);
```

Die Formatierung bei *printf* wird mittels Formatierungszeichen realisiert. Häufig benutzte Zeichen sind:  
- *%d* &nbsp; Decimal signed integer (also *%i*)
- *%o* &nbsp; Octal integer
- *%x* &nbsp; Hex integer (also *%X*)
- *%u* &nbsp; unsigned integer
- *%c* &nbsp; Character
- *%s* &nbsp; String
- *%f* &nbsp; double/floating
- *%e* &nbsp; double (also *%E*)
- *%g* &nbsp; double (also *%G*)
- *%p* &nbsp; Zeiger

Die Flags müssen nach einem *%* stehen.  
Es können in einem Befehl mehrere Flags verwendet werden. Die entsprechende Anzahl Werte (*\<Wert\>*) ist dann, durch Kommas getrennt, anzufügen.  

**Genauigkeit:** `%8.2f`  
Das heißt z.B., dass ein Bereich von 8 Zeichen für ein float/double-Ausgabe reserviert werden soll. Die letzten beiden Stellen werden für die Nachkommastellen reserviert.  

`%#08x`, z.B. ``printf("%#08x\n", 7);`` &rarr; Output: `0x000007`  

d.h. das *0x* zählt zu den 8 Characters der Ausgabe! Für 8 Digits nach dem *0x* muss es `%#010x` heißen.

&nbsp;  

<a name="ch5-6"></a>
### 5.6 `True` and `False` in C  

The C programming language doesn't have a concept of a boolean variable, i.e. a type class that can be either `true` or `false`. Why bother when you can use numerical values:  
> In C 'true' is represented by any numerical value not equal to 0 and 'false' is represented by 0.  

This fact is usually well hidden and can be ignored, but it does allow you to write  
```c
  int a;
  ...
  if (a != 0)
  // just as
  if (a)
```  

Other possibilities:
1. Just include `<stdbool.h>` if your system provides it. That defines a number of macros, including `bool`, `false`, and `true` (defined to `_Bool`, `0`, and `1` respectively).

2. 'Creating' an enum *boolean* int type via `typedef`  
   ```c
    typedef int bool;
    enum { false, true };
   ```

3. 'Creating' an enum *boolean* type via `typedef`  
   ```c
    typedef enum {FALSE = 0, TRUE} bool;
   ```

&nbsp;  

<a name="ch5-7"></a>
### 5.7 Konstruktor in C++  

```cpp
QwinHost::QWinHost(QWidget *parent, Qt::WindowFlags f) : QWidget(parent, f), wndproc(0), own_hwnd(false) { 
  ...
}
```  

Memberlisten:  
Initialisieren Sie Klassenmember aus Konstruktorargumenten durch die Verwendung einer Memberinitialisierungsliste. Bei dieser Methode wird die direkte Initialisierung verwendet, die effizienter als die Verwendung von Zuweisungsoperatoren im Konstruktortextteil ({...}) ist.

&nbsp;  

<a name="ch5-8"></a>
### 5.8 Das Schlüsselwort ``pragma``  

- `#pragma once`  
   In the C and C++ programming languages, **pragma once** is a non-standard but widely supported preprocessor directive designed to cause the current source file to be included only once in a single compilation. Thus, ``#pragma once`` serves the same purpose as **include guards**, but with several advantages, including: less code, avoidance of name clashes, and sometimes improvement in compilation speed. On the other hand, ``#pragma once`` is not necessarily available in all compilers and its implementation is tricky and might not always be reliable.  
   
&nbsp;  

<a name="ch5-9"></a>
### 5.9 `Handle` in C++  

A *handle* is a pointer or index with no visible type attached to it. Usually you see something like:  
```c
typedef void* HANDLE;
HANDLE myHandleToSomething = CreateSomething();
```
e.g. HANDLE is a typedef defined in the *winnt.h* file in Visual Studio (Windows)

So in your code you just pass HANDLE around as an opaque value.  
In the code that uses the object, it casts the pointer to a real structure type and uses it:  

```c
int doSomething(HANDLE s, int a, int b) {
     Something* something = reinterpret_cast<Something*>(s);
     return something->doit(a, b);
 }
```
A handle can be anything from an integer index to a pointer to a resource in kernel space. The idea is that they provide an abstraction of a resource, so you don't need to know much about the resource itself to use it.  

For instance, the HWND in the Win32 API is a handle for a Window. By itself it's useless: you can't glean any information from it. But pass it to the right API functions, and you can perform a wealth of different tricks with it. Internally you can think of the HWND as just an index into the GUI's table of windows (which may not necessarily be how it's implemented, but it makes the magic make sense).  

A Handle can be useful for saving states (among others). If u have data in a structure like an *std::vector*. Your object may be at different memory locations at different times during execution of a program, which means your pointer to that memory will change values. With a handle it never changes, it always references your object. Imagine saving a state of a program (like in a game) - you wouldn't save out a pointer location to data and later import the data again and try to get that address in memory. You can however save out a Handle with your data, and import the data and handle.  

> The key thing is that when you have a "handle", you neither know nor care how that handle actually ends up identifying the thing that it identifies, all you need to know is that it does.  

&nbsp; 

<a name="ch5-10"></a>
### 5.10 'Exceptions' - `Try / Catch`  

C++ bietet einen Mechanismus, der es ermöglicht einen Block von Anweisungen gegen Abstürze zu sichern. Alle darin auftretenden Ausnahmefehler werden einem Behandlungsblock zugeleitet.  

Der gesicherte Anweisungsblock wird durch das Schlüsselwort `try` eingeleitet. Der Fehlerbehandlungsblock beginnt mit `catch`.  

```c
try {...}    // zu sichernder Code
catch {...}  // Code zur Fehlerbehandlung
```

Man nennt einen solchen Fehler `Exception`. Tritt eine solche Ausnahme in einem try-Block auf, dann wird die Verarbeitung in dem behandelnden catch-Block fortgesetzt.  

**Wirkungskreis**  
Eine Ausnahmebehandlung wirkt nicht nur auf den Block selbst, sondern auch auf alle innerhalb des Blocks aufgerufenen Funktionen. Dadurch kann die Fehlerbehandlung an einer zentralen Stelle durchgeführt werden.  
Außerdem kann zusätzlich an jeder Stelle des Programms eine Ausnahmebehandlung stattfinden. Sobald es zu einem Fehler kommt, wird die nächste `catch`-Anweisung verwendet, die auf den Ausnahmetyp passt. Um die nächste Ausnahmebehandlung zu finden, wird die Aufrufreihenfolge rückwärts durchlaufen. Dadurch wird immer die Ausnahmebehandlung verwendet, die der Fehlerstelle am nächsten ist.  

&nbsp;

**`throw` - Eigene Ausnahmen erzeugen**  
Besonders interessant ist es, eigene Ausnahmesituationen zu definieren. Der Befehl `throw` erzeugt eine solche Ausnahme. Er bricht die Verarbeitung sofort ab und springt direkt in die passende Ausnahmebehandlung.  
```c
void TuWas(int prob) {
  ...
  if (prob > 0) {
    throw 0;
  }
}

int main() {
  try {
    ...
    TuWas(1)
  }
  catch(int a) {
    if (a==0) {...}
  }
}
```
Der Befehl `throw` in der Funktion 'TuWas()' löst eine Ausnahme aus, wenn der Parameter 'prob' größer als 0 ist. Die Verarbeitung wird im 'catch'-Block fortgesetzt. Hat der 'catch'-Block 'int' als Parameter, bearbeitet er nur Ausnahmen, die durch einen 'throw'-Befehl mit einer Zahl als Argument ausgelöst wurden. Um andere Parameter zu bearbeiten, wurde einfach ein weiterer 'catch'-Block mit einem (oder mehreren) anderen Parametertyp(en) angehängt.  

&nbsp;

**Fehlerklassen**  
Man kann auch eigene Klassen erstellen, die als Parameter für 'catch' verwendet werden können.  
```c
#include <iostream>
using namespace std;

class KeineDatenMehr {
  public:
    KeineDatenMehr(int a) {
      nr=a;
    }
    void MeldeFehler() {
      cout << nr;
    }
  private:
    int nr;  
}

void TuWas (int prob) {
  if (prob == 0) {
    throw KeineDatenMehr(0);
  }
}

int main () {
  try { TuWas(0); }
  catch(KeineDatenMehr &fehler) {
    fehler.MeldeFehler();
  }
}
```
In der Fehlerklasse lassen sich Informationen über die Fehlerursache hinterlegen. Außerdem können in der Fehlerklasse Funktionen zur Fehlerbehandlung eingebaut werden.  

&nbsp;

**Polymorphie**  
Um verschiedene Fehlersituationen zu behandeln, bietet es sich an, eine Basisklasse für alle Fehlerklassen zu schreiben. Darin implementiert man, was allen Fehlersituationen gemeinsam ist. Vorteil ist, dass nur ein 'catch'-Block nötig ist um alle Fehlertypen abzufangen.  
```c
#include <iostream>
using namespace std;

class meaCulpa {
  public:
    virtual void MeldeFehler()=0;
};
class KeineDatenMehr : public meaCulpa {
  public:
      KeineDatenMehr(int a) {nr=a;}
      void MeldeFehler() {...}
  private:
      int nr;
};

class QuelleFehlt : public meaCulpa {
  public:
    QuelleFehlt() {}
    void MeldeFehler() {...}
};

void TuWas (int prob) throw (KeineDatenMehr, QuelleFehlt) {
  if (prob == 0) {
    throw KeineDatenMehr(8);
  }
  if (prob == 1 ) {
    throw QuelleFehlt();
  }
}

int main () {
  try {
    TuWas(0);
  }
  catch(meaCulpa &fehler) {
    fehler.MeldeFehler();
  }
}
```
Wie immer bei der Polymorphie wird ein Zeiger auf das übergebene Objekt verwendet, um die virtuelle Funktion aufzurufen. Das Objekt kennt sich selbst und ruft über die eigene VTable die zugehörige Funktion 'MeldeFehler()' auf.  
Im Code-Beispiel wurde der Funktion 'TuWas()' eine Deklaration hinzugefügt, die anzeigt, welche Ausnahmen sie auslöst. Diese Informationen sollen darauf hinweisen, dass die Funktion 'throw'-Befehle enthält. Der Compiler würde einen Fehler werfen, wenn die Funktion versucht, eine Ausnahme auszulösen, die in der Deklaration nicht angekündigt ist.  

&nbsp;

&nbsp;

# Bibliotheken, API's und *make*  

<a name="ch6-1"></a>
### 6.1 Library Basics  

Eine Library (Bibliothek) ist eine Anwendung von Funktionen, die bereits in kompilierter Form vorliegen. Sie besteht aus zwei Teilen: dem Archiv und dem Interface in Form von Headern. Hier wird vorerst nur auf statische Libraries für den C-Compiler eingegangen werden. In der Regel enden sie auf die Dateinamenerweiterung `.a`.

- Zunächst wird der Quellcode benötigt, d.h. eine \*.c-Datei mit den Funktionen, aber keine 'main'-Funktion
- Da eine Library lediglich kompiliert und assembliert, aber nicht gelinkt werden soll, muss das beim Compileraufruf berücksichtigt werden. Der Kommandozeilenschalter dafür ist `-c`, z.b.  
  ```c
  $gcc -c -ggdb -02 libfunc01.o libfunc01.c
  ```
- Typdefinitionen und programmglobale Variablen sind am Besten in der Header-Datei aufgehoben
- Wenn Funktionen in der Code-Datei Zeiger zurückgeben, dann müssen dafür modulglobale Variablen, d.h. innerhalb einer gesamten Programmdatei (Speicherung im Datensegment des Speichers).
- Das Archivierungsprogramm `ar` wird dazu verwendet, um die kompilierten Objektfiles zu einer 'Library' zusammenzufügen:
  ```c
  $ ar -rcs libmylib.a libfunc01.o
  ```
- Den Inhalt der frisch erzeugten Library kann man sich mit 'nm' anzeigen lassen:
  ```c
  $ nm -s libmylib.a
  ```
&nbsp;

**Fertige Library**  
Es existieren jetzt zwei Dateien, die zum Export der Library benötigt werden:  
1. 'mylib.h', in der das Interface dokumentiert ist
2. 'libmylib.a', die Library selber in kompilierter Form

Hat man die Library jetzt in seinem Projektordner vorliegen, muss man für die Verwendung die Library mit linken, z.B.
```c
$ gcc -ggdb -02 -o ... -mylib
```

`-mylib` := sagt dem Linker, dass er die Library 'libmylib.a' beim Linken verwenden soll (alle Libraries haben das Prefix 'lib', welches hier nicht angegeben werden darf!)


&nbsp; 

<a name="ch6-2"></a>
### 6.2 [Win API] `#define DECLARE_HANDLE(n)`  
```c
#define DECLARE_HANDLE(n) typedef struct n##__{int i;}*n

DECLARE_HANDLE(HWND);
```
> "##" means connect the parameter.

So the macro equals:
`typedef struct HWND__{int i;}*HWND`

The main purpose of this construct is to prevent the misuse of handles. If all handles are simply *void \** or *int* or *long long* or some other basic type, there is nothing to prevent you from using one instead of another. A pointer to a struct HWND__ and pointer to struct HBITMAP__ isn't the same thing, so if you have a the following code:  
```c
HWND hwnd;
HBITMAP hbmp;

hbmp = GetBitmap(...);
hwnd = hbmp;    // gives compiler error. 
```
It's a fairly classic technique to ensure that you get unique types for something that the API supplier don't want to provide the true declaration for. 

Handles don't actually point to anything in memory; they are just used to refer to objects (files, resource, semaphores, windows) when making calls to the Windows API. While they're nothing more than just indexes into kernel's object tables, the developers decided that they make it a pointer to an unused structure which would make them "opaque" and cause less confusion between other types. The *DECLARE_HANDLE* is a function macro that does just that - declaring opaque types for handles.

&nbsp; 

<a name="ch6-3"></a>
### 6.3 [Win API] `HWND` (Fenster Handle)  

Handle `HWND` is declared in *windef.h*:  
```c
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)

DECLARE_HANDLE            (HWND);
DECLARE_HANDLE            (HHOOK);

#endif /* WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP) */ 
```

HWND is a "handle to a window" and is part of the Win32 API . HWNDs are essentially pointers (IntPtr) with values that make them (sort of) point to a window-structure data. As they are only intPtr, type safety is not automatically given. To prevent misuse, the following is done &rarr; see [chapter 6.2](#ch6-2) above.   

&nbsp;

- Beziehung zwischen einem C++-Fensterobjekt und einem `HWND`
  Das Window- Objekt ist ein Objekt der C++- ``CWnd`` Klasse (oder einer abgeleiteten Klasse), die vom Programm direkt erstellt wird. Dies geschieht als Reaktion auf den Konstruktor-und dekonstruktoraufruf Ihres Programms. Das Windows- Fenster hingegen ist ein **undurchsichtiges Handle für eine interne Windows-Datenstruktur**, die einem Fenster entspricht und Systemressourcen beansprucht, wenn Sie vorhanden sind. Ein Windows-Fenster wird durch ein "Fenster Handle" ( ``HWND`` ) identifiziert und wird erstellt, nachdem das- ``CWnd`` Objekt durch einen- ``Create`` Member der-Klasse erstellt wurde ``CWnd`` . Das Fenster kann entweder durch einen Programm Rückruf oder durch eine Benutzeraktion zerstört werden. Das Fenster Handle wird in der m_hWnd Member-Variable des Window-Objekts gespeichert. In der folgenden Abbildung wird die Beziehung zwischen dem C++-Fenster Objekt und dem Windows-Fenster angezeigt.  

  ![hwnd](../assets/pics/hwnd01.png)  

- Funktion *EnumWindows*  
  Function enumerates all top-level windows currently on the screen by passing the handle to each window to an application-defined callback function. *EnumWindows* continues until the last top-level window is enumerated or the callback function returns FALSE.  
  ```c
  BOOL WINAPI EnumWindows (WNDENUMPROC lpEnumFunc,..., LPARAM lParam); 
                                  (1)                      (2)
  ```
  (1) A pointer to an application-defined callback function (&rarr; 'EnumWindowsProc')  
  (2) An application-defined value to be passed to the callback function  

- Funktion *EnumWindowsProc*  
  A user defined function used with function *EnumWindows* (&rarr; argument (1)). It receives top-level window handles. *EnumWindowsProc* is a placeholder for the application-defined function name.  
  ```c
  BOOL CALLBACK EnumWindowsProc (HWND hwnd,..., LPARAM lParam); 
                                  (1)                      (2)
  ```
  (1) A handle to a top-level window  
  (2) The application-defined value given in *EnumWindows*  

&nbsp; 

<a name="ch6-4"></a>
### 6.4 *The C++ Standard Template Library* ('Container-Klasse')  

> STL := The Standard Template Library (STL) is a set of C++ template classes to provide common programming data structures and functions such as lists, stacks, arrays, etc. It is a library of container classes, algorithms, and iterators. It is a generalized library and so, its components are parameterized.  

&nbsp;

Flowchart of Adaptive Containers and Unordered Containers  
![stl](../assets/pics/stl_01.png)  

Flowchart of Sequence conatiners and ordered containers  
![stl](../assets/pics/stl_02.png)  

&nbsp;

**Template classes**

- `map`

  Der Container `map` nimmt zwei Arten von Elementen auf, der Erste ist der Suchschlüssel (oder 'key') und der Zweite ist das eigentliche Datenelement, das durch den Schlüssel gefunden werden soll. So werden bei der Definition eines Map-Containers zwei Typen angegeben: der Erste für den Schlüssel, der Zweite für den Wert. Die eckigen Klammern werden von der `map` so überladen, dass der Schlüssel dazwischen angegeben wird. Der gesamte Ausdruck bezeichnet dann das Datenelement.  

  ```c
  #include <string>
  #include <maps>

  int main () {
    map <string, string> Kennzeichen;
    Kennzeichen["HH"] = 'Hansestadt Hamburg';
  }
  ```
  &nbsp;

  **Functions**  

  - *find()*  
     Wollen Sie prüfen, ob es ein Element überhaupt gibt, sollten Sie die Elementfunktion 'find()' verwenden:
     ```c
     if (Kennzeichen.find("KI")==Kennzeichen.end()) {
       cout << "Nicht gefunden!" << endl;
     }
     ```
  - *size()*  
     Returns the number of elements in the map.  
  - *pair insert(keyvalue, mapvalue)*  
    Adds a new element to the map.  
  - *erase(iterator position)*  
    Removes the element at the position pointed by the iterator.  
  - *erase(const g)*  
    Removes the key value ‘g’ from the map.  

&nbsp; 

<a name="ch6-5"></a>
### 6.5 [make] Call 'Makefile' in Subdirectory  

If you're looking to perform more tasks within 'some_directory', you need to add a semi-colon and append the other commands as well. Note that you cannot use newlines as they are interpreted by 'make' as the end of the rule, so any newlines you use for clarity needs to be escaped by a backslash.  
```c
all: 
    echo "I'm in some_dir"; \
    gcc -Wall -o myTest myTest.c
```

Note also that the semicolon is necessary between every command even though you add a backslash and a newline. This is due to the fact that the entire string is parsed as a single line by the shell. You should use '&&' to join commands, which means they only get executed if the preceding command was successful.  
```c
all: 
    echo "I'm in some_dir" && \
    gcc -Wall -o myTest myTest.c
```

This is especially crucial when doing destructive work, such as clean-up, as you'll otherwise destroy the wrong stuff.  

A common usage is to call 'make' in the subdirectory, the rule would look like this:
```c
all: 
    $(MAKE) -C some_dir all
```
which will change into 'some_dir' and execute the 'Makefile' in there with the target 'all'. As a best practice use '$(MAKE)' instead of calling 'make' directly, as it'll take care to call the right make instance, as well as provide slightly different behaviour when running using certain switches, such as '-t'.  

For the record:  
'make' always echoes the commandit executed (unless explicitly suppressed), even if it has no output, which is what you're seeing.

&nbsp;

<a name="ch6-6"></a>
### 6.6 String  

Um String-Funktionen nutzen zu können, muss die Bibliothek *string.h* eingebunden werden.  
&nbsp;

**strlen (char \*str)**  
Funktion ermittelt die Länge eines Strings bzw. die Anzahl seiner Zeichen.  

&nbsp;

**char \*strcpy (char \*dest, char \*src)**  
Mit *string copy* können wir den Inhalt eines Strings kopieren.  
- *\*dest* ist Zeiger auf Ziel-Array
- *\*src* ist Zeiger auf Quell-Array

Rückgabewert ist char-Zeiger auf Ziel-Array.

```c
char textA[5] = "abc";
printf("textA: %s", textA);    // textA: abc

strcpy(textA, "xyz");
printf("textA: %s", textA);    // textA: xyz
```

**char \*strcpy (char \*dest, char \*src, int n)**  
Mit *strcpy* kopiert man n Zeichen von *src* nach *dest*. Das String-Ende-Zeichen (*\\0*) muss manuell gesetzt werden.  

&nbsp;

**char \*strcat (char \*dest, char \*src)**  
Mit *strcat* können wir Strings verketten, also aneinenaderhängen. Das Ergebnis wird in *dest* gespeichert.

**char \*strncat (char \*dest, char \*src, int n)**  
Mit *strncat* können wir n Zeichen ans *src* anhängen.  

&nbsp;

**int \*strcmp (char \*str1, char \*str2)**  
Mit *strcmp* können wir zwei Strings vergleichen.  
Rückgabewerte:  
- 0 := die Strings sind gleich
- \>0 := das erste ungleiche Zeichen in *str1* ist größer als in *str2*
- \<0 := das erste ungleiche Zeichen in *str1* ist kleiner als in *str2*  

**int \*strncmp (char \*str1, char \*str2, int n)**  
Mit *strncmp* und dem Parameter n können wir die ersten n Zeichen der Strings vergleichen.

&nbsp;

**char \*strstr (char \*string, char \*needle)**  
Mit *strstr* können wir nach Zeichenketten in einem String suchen. Der Rückgabewert ist die Adresse vom Anfang des gefundenen *needle* in String (gespeichert in *needle*) ansonsten *NULL*.  

&nbsp;

**char \*strchr (char \*s, int c)**  
Mit *string char* können wir ein Zeichen in einem String suchen. Das zu suchende Zeichen wird mit dem Parameter *c* als ASCII-Code übergeben. Rückgabewert ist *NULL* wenn Zeichen nicht gefunden, ansonsten Adresse des ersten gefundenen Zeichens.  

&nbsp;

**char \*strtok (char \*str1, char \*delimiters)**  
Mit *strtok* können wir einen String anhand von Trennzeichen zerteilen und die einzelnen Abschnitte herauslesen. Die Trennzeichen werden im Parameter *delimiter* übergeben.  
Beim ersten Aufruf muss *strtok* mit einem String initialisiert werden. Die Rückgabe ist hierbei der erste Abschnitt. Bei Folgeaufrufen wird statt *string* der *NULL*-Wert übergeben, da *strtok* bereits initialisiert ist und intern einen Zeiger auf *String* gespeichert hat. Der Zeiger *ptr*, welcher den Rückgabewert abfängt, zeigt auf das erste Zeichen des jeweiligen Abschnitts in *string*. Das jeweilige Ende wird mit *\\0* in *string* gesetzt, d.h. der String wird verändert. Man sollte bei *strtok* immer eine Kopie des Strings verwenden.  

```c
char string[] = "Kurt; ist, der; Größte";
char delimiter[] = ",;";
ptr strtok(string, delimiter);    // Initialisieren und ersten Abschnitt erstellen

while (ptr != NULL) {
  printf("Ausgabe: %s\n", ptr);
  ptr = strtok(NULL, delimiter);
}

// Ausgabe: Kurt
// Ausgabe: ist 
// Ausgabe: der
// Ausgabe: Größte
```

&nbsp;

&nbsp;

# How To's

<a name="ch7-1"></a>
### 7.1 Emulation <font size="-1">(hier 'Prozessor Emulation')</font>  

Basic Idea  
> "Emulation is realised by handling the behaviour of the processor and the individual components.  
> You build each individual piece of the system in SW and then connect the pieces much like wires do in hardware."  
 
&nbsp;

Two ways of processor emulation:  
1. **Dynamic Recompilation**  
2. **Interpretation**   

&nbsp;

**(1) Dynamic Recompilation**  
With dynamic recompilation, you iterate over the code much like interpretation, but instead of executing opcodes, you build a list of operations. Once you reach a branch instruction, you compile this list of operations to machine code for your host platform, then you cache this compiled code and execute it. Then, when you hit a given instruction group again, you only have to execute the code from the cache.  

**(2) Interpretation**  

![emu](../assets/pics/emulators.png)  

An emulator is a computer program that mimics the internal design and functionality of a computer system (*System A*). It allows users to run software designed for this specific system (*System A*) to run on a totally different computer system or architecture (*System B*).  

In case of an emulator, we chose not to re-implement the desired game for our native system. Instead, we re-create the environment with a computer program which allows us to run the original machine code (so the Assembly code!) of the game. A benefit of this is that it won't just allow us to run that one game, but also any other application developed for that platform.  

For start writing an emulator, it is important to find as much information as possible about the system you want to emulate. How much memory and registers are used, with what size? What architecture is used? Get hold of technical documents that describe the *instruction set*.  

*Interpretational Emulation* bedeutet  
- den (oftmals kleinen) Speicher des zu emulierenden Geräts in eine Variable (Array) zu packen, d.h. aus  
  ``4k memory`` wird `unsigned char memory[4096];`  
- das gleiche gilt für Register, d.h. aus  
  `8-bit GP register` wird `unsigned char reg[16];`  
- oder für Grafik-Speicher, d.h. aus  
  `2048 pixels (64*32)` wird `unsigned char gfx[64*32];`  
- bestimmte Register und spezielle Counter überführen, d.h. aus  
  `Index Register I` wird `unsigned short I;`  
  `program counter pc` wird `unsigned short pc;`  
  `16 levels of stack` wird `unsigned short stack[16];`  
  ``stack pointer sp`` wird `unsigned short sp;`  
- für das *instruction set* des Prozessors:  
  Bereitstellen von Funktionen oder 'switch-case'-Anweisungen, d.h. ein Mappen der Ursprungs-Assembly-Befehle auf Code in Hochsprache (z.B. C) des *Systems B*.  

Das heisst der spätere Ablauf auf dem Zielsystem wäre dann:  
   1. Laden des Ursprungs-Assembly-Codes in Memory-Array  
   2. Lesen des opcodes in Array entsprechend des Wertes des program counters (pc)  
   3. Übersetzen/Ausführen des jeweils entsprechenden Codes in C auf Zielsystem  
   4. Compiler übersetzt den Code in Assembler ausführbar auf *System B*  
   5. Ausführung auf *System B* 

&nbsp; 

<a name="ch7-2"></a>
### 7.2 Code optimization turned off for debugging in 'Release' version  
When we compile a program, we often need to choose one of possible "configurations". Visual Studio creates two of those for a new C++ project, called "Debug" and "Release". As their names imply, the first one is mostly intended to be used during development and debugging, while the other should be used to generate the final binary of the program to be distributed to the external users. Each of these configurations actually sets multiple parameters of the project and you can change them.  
Debug configuration is all about having the optimizations disabled (which allows full debugging functionality and also makes the compilation time short), while Release has the optimizations enabled (which obviously makes the program run faster).  

Some bugs just don't happen in Debug, e.g. due to uninitialized memory containing consistent 0xCCCCCCCC instead of garbage data, or a race condition between threads not occurring because of a different time it takes to execute certain functions. In any case, sometimes we need to **investigate bugs occurring in Release configuration**. Not all hope is lost then, because in Visual Studio the debugger still works, just not as reliably as in Debug. So here the following line of code comes handy:  

```c
#pragma optimize("", off)
```

The custom Microsoft preprocessor macro above, put at the beginning of a .cpp file or just before your function of interest, disables all the compiler optimizations from this point until the end of the file. This is making its debugging nice and smooth, while the rest of the program behaves as before.  

&nbsp; 

<a name="ch7-3"></a>
### 7.3 Digital Filter Implementation  

**IIR Tiefpass (Tiefpass 1.Ordnung)**  
Er verhält sich (mit Ausnahme dass er digital ist) wie ein analoger RC-Tiefpass (aus Widerstand und Kondensator). Es ist sehr schnell berechnet und gut wenn hochfrequente Störungen aus einem Eingabesignal entfernt werden sollen. Zwei Parameter werden benötigt, deren Summe aber 1 ergeben muss. Je höher coeff[1], desto stärker werden Störungen entfernt, desto langsamer ändert sich aber auch die Ausgabe des Filters. Je höher coeffs[0], desto schneller reagiert die Ausgabe, aber es kommt auch mehr Rauschen durch.  

<details><summary markdown="span">IIR FILTER</summary>  
  ```c  
    #include <stdlib.h>

    // This is the only variable that this filter needs, the coefficients below are constant.
    real_t old_value;

    // The coefficients of our filter. We use a simple 1st order low pass here,
    // so we have two values. The sum of both must be 1. You can add more weight
    // to the new value or to the old value (which includes the all the previously
    // calculated filter results).

    real_t coeffs[2] = {
      0.5,  // The weight of the new value
      0.5   // The weight of the old value
    };

    // Here we initialise our IIR filter.
    
    void filter_init() {
      old_value = 0.0;
    }

    // This function is called every cycle. Calculates the new output value and
    // saves it in last_value for the next cycle.
    
    // @param double new_value
    // @return double
 
    real_t filter(real_t new_value) {
      // Calculate y = a0 * x(k-0) + a1 * x(k-1)
    return old_value = coeffs[0] * new_value + coeffs[1] * old_value;
    }
  ```
</details>

&nbsp;

**Moving Average**  
Ein Moving Average Filter (oder Sliding Window Filter) bildet den Mittelwert über die letzten N Eingabewerte. Wie der IIR Filter oben ist er schnell berechnet, reagiert aber schneller bei moderater Rauschunterdrückung. Nachteil: Er braucht Speicher, was auf kleinen Mikrocontrollern ein Problem sein könnte. Der Algorithmus berechnet einfach die Summe der Vergangenheitswerte geteilt durch die Anzahl an Vergangenheitswerten (Mittelwert eben). Mit einem kleinen Trick rechnen wir das nicht immer wieder aus, stattdessen speichern wir die Summe in einer Variable. Wenn ein neuer Eingabewert kommt, so subtrahieren wir den ältesten Wert und addieren den neuen. Danach müssen wir diese Summe noch durch die Anzahl an Elementen teilen und haben das neue Ergebnis. Erstmal die Floating Point Variante:  

<details><summary markdown="span">MOVING AVERAGE (FLOAT)</summary>  
  ```c
  
    // The size of our filter. We specify it in bits
    #define FILTER_SIZE (8)
    
    real_t filter_buffer[FILTER_SIZE];
    
    // Here we store the sum of all history values
    real_t filter_sum;
    
    // This is the actual position of the ring buffer.
    real_t *filter_position;
    
    // Here we initialise our filter. In this case we only set the
    // initial position and set all buffer values to zero.
    void filter_init() {
      register int i;
      filter_sum = 0;
      filter_position = filter_buffer;
      // alternatively memset(filter_buffer, 0, sizeof(filter_buffer) * sizeof(unsigned int))
      for(i=0; i<FILTER_SIZE; i++) filter_buffer[i] = 0;
    }
    
    // This function is called every cycle. It adds substracts the oldest value from
    // the sum, adds the new value to the sum, overwrites the oldest value with the
    // new value and increments the ring buffer pointer (with rewind on overflow).

    // @param double new_value
    // @return double

    real_t filter(real_t new_value) {
      // Substract oldest value from the sum
      filter_sum -= *filter_position;
    
      // Update ring buffer (overwrite oldest value with new one)
      *filter_position = new_value;
    
      // Add new value to the sum
      filter_sum += new_value;
    
      // Advance the buffer write position, rewind to the beginning if needed.
      if(++filter_position >= filter_buffer + FILTER_SIZE) {
        filter_position = filter_buffer;
      }
    
      // Return sum divided by FILTER_SIZE, which is faster done by right shifting
      // The size of the ring buffer in bits. ( filter_sum / 2^bits ).
      return filter_sum / FILTER_SIZE;
    }
  ```
</details>  

&nbsp;

Nun das Selbe mit Integern. Vor allem wenn keine Floating Point Einheit im Controller ist spart das viel Zeit. Beim Dividieren kann ebenfalls eingespart werden, indem man statt /2 zu rechnen jeweils ein mal die Bits der Zahl nach rechts schiebt. Das lässt sich also für alle Puffergrößen von 2^BITS machen. Der Ringbuffer im Beispiel hat 8 Werte, und mit summe >> 3 haben wir die Summe durch 8 geteilt.  

<details><summary markdown="span">MOVING AVERAGE (INTEGER)</summary>  
  ```c

  // The size of our filter. We specify it in bits
  #define FILTER_SIZE_IN_BITS (3)
  #define FILTER_SIZE ( 1 << (FILTER_SIZE_IN_BITS) )
  
  uint16_t filter_buffer[FILTER_SIZE];
  
  // Here we store the sum of all history values
  uint32_t filter_sum;
  
  // This is the actual position of the ring buffer.
  uint16_t *filter_position;
  
  // Here we initialise our filter. In this case we only set the
  // initial position and set all buffer values to zero.
  void filter_init() {
    register int i;
    filter_sum = 0;
    filter_position = filter_buffer;
    // alternatively memset(filter_buffer, 0, sizeof(filter_buffer) * sizeof(unsigned int))
    for(i=0; i<FILTER_SIZE; i++) filter_buffer[i] = 0;
  }
  
  // This function is called every cycle. It adds substracts the oldest value from
  // the sum, adds the new value to the sum, overwrites the oldest value with the
  // new value and increments the ring buffer pointer (with rewind on overflow).

  // @param double new_value
  // @return double
  real_t filter(real_t new_value) {
    // Substract oldest value from the sum
    filter_sum -= *filter_position;
  
    // Update ring buffer (overwrite oldest value with new one)
    *filter_position = (uint16_t) new_value;
  
    // Add new value to the sum
    filter_sum += (uint16_t) new_value;
  
    // Advance the buffer write position, rewind to the beginning if needed.
    if(++filter_position >= filter_buffer + FILTER_SIZE) {
      filter_position = filter_buffer;
    }
  
    // Return sum divided by FILTER_SIZE, which is faster done by right shifting
    // The size of the ring buffer in bits. ( filter_sum / 2^bits ).
    return (real_t) (filter_sum >> FILTER_SIZE_IN_BITS);
  }
  ```
</details> 

&nbsp;

**FIR Filter**  
Die folgenden Quelltexte sind Implementationen eines zyklisch aufgerufenen FIR Filters. Wie beim Moving Average Filter (der ein FIR-Filter ist) müssen auch hier die Vergangenheitswerte gespeichert werden. Zudem gibt es einen Speicherbereich mit Koeffizienten, der genau so groß ist wie der Wertepuffer. Alles was der Filteralgorithmus tun muss, ist jeden gespeicherten Vergangenheitswert mit dem dazugehörigen Koeffizienten zu multiplizieren und all diese Produkte zum Endergebnis aufzuaddieren. Die Anzahl und Werte der Koeffizienten bestimmen dabei, was der Filter tut. Er kann Tiefpass, Hochpass, Bandpass, Bandsperre und vieles mehr sein. FIR Filter sind ein derart scharfes Messer im Schrank der Signalverarbeitung, dass Prozessoren darauf ausgelegt werden sie schnell berechnen zu können. Vor allem in DSPs sieht man daher **MAC-Operationen (Multiply and Accumulate)**, d.h. in einem Schritt multiplizieren sie zwei Zahlen und addieren das Ergebnis zu einer Summe hinzu. Abhängig von den Features eines Controllers sollte dann auch besser von C auf Assembly ausgewichen werden (z.B. gibt es auch Prozessoren, die die MAC-Operation rechnen und im selben Schritt das nächste Wert-Koeffizient-Paar anvisieren, usw. usw.). Besser lesbar ist jedoch dieses Beispiel in C. Die Koeffizienten habe ich so gewählt, dass dieser FIR identisch mit dem Moving Average Filter ist. Es ist auch ein leicht nachvollziehbares Beispiel: Statt zum Schluss **Summe / N** zu rechnen wird hier jeder Vergangenheitswert mal **1/N** gerechnet. "Da kommt das Selbe raus." Für andere Filterkoeffizienten lohnt sich ein Blick in die **Signal Toolbox von GNU Octave**. (Die Software ist kostenlos).  

Erstmal mit Fließkommazahlen: Der Algorithmus ist recht selbsterklärend, zwei Sachen seien aber noch angemerkt:  

- Wir füllen den Ringpuffer rückwärts, denn dann sind die Vergangenheitswerte zum Rechnen bereits richtig geordnet. D.h. der vorherige Wert ist eins nach vorn, der davor zwei nach vorn usw.  

- Wir rechnen in zwei Schleifen, damit wir uns die Abfrage, ob wir am Ende des Ringpuffer-Speichers angekommen sind, in der Schleife erspart bleibt. Es kommt richtig raus wenn wir erst bis zum Ende des Puffers arbeiten, dann die Pufferposition rücksetzen und bis zum Ende der Koeffizienten rechnen.  

<details><summary markdown="span">FIR FILTER</summary>  
  ```c

    #include <stdlib.h>
    
    // The size of our filter.
    #define FIR_FILTER_SIZE (8)
    
    // These are coefficients of the FIR filter. In this case the size is 8 and
    // all values are 1/8. This means it works exactly like a sliding window
    // (moving average) filter.
    real_t fir_coeffs[FIR_FILTER_SIZE] = {
      (1.0/8), (1.0/8), (1.0/8), (1.0/8),
      (1.0/8), (1.0/8), (1.0/8), (1.0/8)
    };
    
    // This is the history buffer of the values. It is used as a ring buffer.
    real_t fir_buffer[FIR_FILTER_SIZE];
    

    // This is the actual position of the ring buffer.
    real_t *fir_position = NULL;
    
    // Here we initialise our FIR filter. In this case we only set the
    // initial position and set all buffer values to zero.
    void filter_init() {
      fir_position = fir_buffer;
      int i;
      for(i=0; i<FIR_FILTER_SIZE; i++) {
        fir_buffer[i] = 0;
      }
    }
    
    // This function is called every cycle. It adds the new value (e.g. read from
    // an analog input) and accumulates the products of all history values with
    // their corresponding coefficient.
    // @param double new_value
    // @return double
    real_t filter(real_t new_value) {
      // 1st coeff position is at pointer position fir_coeffs
      real_t *p_coeff  = fir_coeffs;
    
      // 1st buffer position is at the actual write position
      real_t *p_buffer = fir_position;
    
      // This is our function result
      real_t result = 0;
    
      // We overwrite the oldest value with the new value. This is now our 1st
      // position to start.
      *fir_position = new_value;
    
      // As the buffer has the same size as the coefficients, we can iterate to
      // the end of the buffer. The p_coeff pointer cannot overflow here.
      while(p_buffer < fir_buffer + FIR_FILTER_SIZE) {
        // Multiply and accumulate
        result += (*p_coeff) * (*p_buffer);
    
        // Next coeff, next buffer position
        p_coeff++;
        p_buffer++;
      }
    
      // Reset the pointer to the start of the ring buffer and iterate until the
      // p_coeff pointer reaches its end. After this we have MAC'ed all history
      // values with their corresponding coefficients.
      p_buffer = fir_buffer;
      while(p_coeff < fir_coeffs + FIR_FILTER_SIZE) {
        // MAC
        result += (*p_coeff) * (*p_buffer);
        // Increment buffer and coefficient position.
        p_coeff++;
        p_buffer++;
      }
    
      // To finish this, we advance our ring buffer write position and roll over
      // to the beginning if we reached the end of the memory block.
      // Note: We write backwards so that our history time is ascending. 
      if(--fir_position < fir_buffer) {
        fir_position = fir_buffer + FIR_FILTER_SIZE - 1;
      }
    
      // Return our filter result.
      return result;
    }
  ```
</details> 

&nbsp; 

<a name="ch7-4"></a>
### 7.4 Access file in .exe directory  

Paths beginning with "\\" are always relative to the current drive's root directory. If the current drive is "C:", then "settings\\settings.cfg" means "C:\\settings\\settings.cfg".  

Note that you can use "/" in order to avoid escaping everything. So you can use "settings/settigs.cfg".This will be relative to the user's current directory. Note however, that this doesn't necessarily correspond to the directory where the executables resides!  

If you need the directory of the executable, then you need to use a Windows API function to get it:
```c
#include <Windows.h>
...
HMODULE module = GetModuleHandleW(NULL);
WCHAR path[MAX_PATH];
GetModuleFileNameW(module, path, MAX_PATH);
```
Now if you want to open "settings/settings.cfg" relative to the directory of the executable create a pyth that starts with "path" and append "settings/settings.cfg" to it. To create a path of variable "path" and a text use "std::String"  
```c
std::string newPath = path + std::string("settings/settings.cfg")  
```

&nbsp;

&nbsp;

# Warnings and Errors

&nbsp; 

<a name="ch8-1"></a>
### 8.1 'Warning: no previous prototype for \<function\>'  

> A function prototype is a declaration of a function that declares the types of íts parameters.

An empty argument list in a function delaration indicates that the number and type of parameters is not known. You must explictly indicate that the function takes no arguments by using the `void` keyword, e.g.  
```c
void screen_init(void);
```

&nbsp;

&nbsp;  

[Back](../)
