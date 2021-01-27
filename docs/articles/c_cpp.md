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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.6 Die Funktion `main`</font>](#ch1-6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.7 Übersicht Datentypen in C</font>](#ch1-7)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.8 Threads und Prozesse</font>](#ch1-8)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9 Benutzerdefinierte Datentypen</font>](#ch1-9)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9.1 `typedef`</font>](#ch1-9-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9.2 `enum`</font>](#ch1-9-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9.3 `struct`</font>](#ch1-9-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.9.4 `union`</font>](#ch1-9-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.10 Precompiled Header</font>](#ch1-10)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.11 *Header Guard* (oder 'Include Guard')</font>](#ch1-11)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.12 *Calling Convention* (`__stdcall`)</font>](#ch1-12)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.13 Namespaces</font>](#ch1-13)  

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

### 4. Pointer und Arrays   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.1 Vergleich von char-Arrays und Pointern auf Zeichenketten</font>](#ch4-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.2 Das Schlüsselwort ``const`` bei Pointern und Arrays</font>](#ch4-2)  

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

### 6. Bibliotheken und API's   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.1 String</font>](#ch6-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.2 [Win API] `#define DECLARE_HANDLE(n)`</font>](#ch6-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.3 [Win API] `HWND` (Fenster Handle)</font>](#ch6-3)  

### 7. How To's & Special Syntax   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.1 Emulation</font>](#ch7-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.2 Code optimization turned off for debugging in 'Release' version</font>](#ch7-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.3 Digital Filter Implementation</font>](#ch7-3)  

### 8. ...

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

- Include file *xy.h* from parent directory  
`#include "../xy.h"`

&nbsp;

<a name="ch1-6"></a>
### 1.6 Die Funktion `main`  
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

<a name="ch1-7"></a>
### 1.7 Übersicht Datentypen in C  

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

<a name="ch1-8"></a>
### 1.8 Threads und Prozesse  

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

<a name="ch1-9"></a>
### 1.9 Benutzerdefinierte Datentypen  

<a name="ch1-9-1"></a>
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

<a name="ch1-9-2"></a>
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

<a name="ch1-9-3"></a>
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

<a name="ch1-9-4"></a>
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

<a name="ch1-10"></a>
### 1.10 Precompiled Header  

In computer programming, a *precompiled header* is a (C or C++) header file that is compiled into an intermediate form, that is <u>faster to process for the compiler</u>.  

Usage of *precompiled headers* may significantly reduce compilation time, especially when applied to large header files or header failes that include many other header files.

&nbsp;

<a name="ch1-11"></a>
### 1.11 *Header Guard* (oder 'Include Guard')  

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

<a name="ch1-12"></a>
### 1.12 *Calling Convention* (`__stdcall`)  
```c
#define CALLBACK __stdcall
#define WINAPI __stdcall
#define WINAPIV __cdecl
#define APIENTRY WINAPI
```
All functions in C/C++ have a particular calling convention. The point of a calling convention is to establish how data is passed between the caller and callee and who is responsible for operations such as cleaning out the call stack.  

The most popular calling conventions on windows are  
- __stdcall, Pushes parameters on the stack, in reverse order (right to left)
- __cdecl, Pushes parameters on the stack, in reverse order (right to left)
- __clrcall, Load parameters onto CLR expression stack in order (left to right).
- __fastcall, Stored in registers, then pushed on stack
- __thiscall, Pushed on stack; this pointer stored in ECX

&nbsp;

<a name="ch1-13"></a>
### 1.13 Namespaces  

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
if (a != 0)
// just as
if (a)
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

&nbsp;

# Bibliotheken

<a name="ch6-1"></a>
### 6.1 String  

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

&nbsp;  

[Back](../)
