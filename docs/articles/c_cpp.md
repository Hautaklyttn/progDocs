---
layout: default
---

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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.6 `True` and `False` in C</font>](#ch5-5)  

### 6. Bibliotheken   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.1 String</font>](#ch6-1)  

### 7. How To's & Special Syntax   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.1 Emulation</font>](#ch7-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">7.2 `#define DECLARE_HANDLE(n)` (Windows API Code)</font>](#ch7-2)  

### 8. Qt and QML   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">8.1 Qt5 / Qt Quick / QML</font>](#ch8-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">8.1.1 Basic QML concepts</font>](#ch8-1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">8.2 Basics</font>](#ch8-2)  

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
### 7.2 `#define DECLARE_HANDLE(n)` (Windows API Code)  
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

# Qt and QML  

> "Qt is a cross platform development framework written in C++."  

- Qt was originally for user interfaces - now for everything (e.g. databases, XML, WebKits, multimedia, networking, OpenGL, scripting, etc.)
- Qt extends C++ with macros and introspection  

  ````c
  foreach (int value, intList) {...}     // macro

  QObject *o = new QPushButton;
  o->metaObject()->classObject();        // introspection (returns "QPushButton")

  connect(button, SIGNAL(clicked()), window, SLOT (close()));    // macro
  ````

&nbsp; 

<a name="ch8-1"></a>
### 8.1 Qt5 / Qt Quick / QML  
**Qt5** is a complete refreshing of the very successful Qt4 release. Qt5 is focusing on the following:  

- Outstanding graphics:
  Qt Quick 2 is based on OpenGL using a scene graph implementation. The recomposed graphics stack allows a new level of graph effects combined with an ease of use never seen before in this field.
- Developer productivity:
  QML and JavaScript are the primary means for UI creation. The back-end will be driven by C++. The split between JavaScript and C++ allows a fast iteration for front-end developers concentrating on creating beautiful user interfaces and back-end C++ developers concentrating on stability, performance and extending the runtime.  
- Cross-platform portability:  
  It is now possible to port Qt to a wider range of platforms easier and faster. Qt 5 is structured around the concept of Qt Essentials and Add-ons, which allows OS developer to focus on the essentials modules and leads to a smaller runtime altogether.  

&nbsp; 

**Qt Quick** is the umbrella term for the user interface technology used in Qt 5. Qt Quick itself is a collection of several technologies:  
- QML - Markup language for user interfaces  
- JavaScript - The dynamic scripting language  
- Qt C++ - The highly portable enhanced c++ library  

&nbsp; 

![0x](../assets/pics/qt_quick.png)  

&nbsp; 

Similar to HTML, QML is a markup language. It is composed of tags, called types in Qt Quick, that are enclosed in curly brackets: *Item {}*. It was designed from the ground up for the creation of user interfaces, speed and easier reading for developers. The user interface can be enhanced further using JavaScript code. Qt Quick is easily extendable with your own native functionality using Qt C++. In short, the declarative UI is called the front-end and the native parts are called the back-end. This allows you to separate the computing intensive and native operation of your application from the user interface part.  

In a typical project, the front-end is developed in QML/JavaScript. The back-end code, which interfaces with the system and does the heavy lifting, is developed using Qt C++. This allows a natural split between the more design-oriented developers and the functional developers.  

&nbsp; 

The **Qt Essentials modules** are mandatory for any Qt-enabled platform. They offer the foundation to develop modern Qt 5 Applications using Qt Quick 2.  

|Module|Description|
|:---|:---|
|Qt Core|Core non-graphical classes used by other modules.|
|Qt GUI|Base classes for graphical user interface (GUI) components. Includes OpenGL.|
|Qt Multimedia|Classes for audio, video, radio and camera functionality.|
|Qt Multimedia Widgets|Widget-based classes for implementing multimedia functionality.|
|Qt Network|Classes to make network programming easier and more portable.|
|Qt QML|Classes for QML and JavaScript languages.|
|Qt Quick|A declarative framework for building highly dynamic applications with custom user interfaces.|
|Qt Quick Controls 2|Provides lightweight QML types for creating performant user interfaces for desktop, embedded, and mobile devices. These types employ a simple styling architecture and are very efficient.|
|Qt Quick Dialogs|Types for creating and interacting with system dialogs from a Qt Quick application.|
|Qt Quick Layouts|Layouts are items that are used to arrange Qt Quick 2 based items in the user interface.|
|Qt Quick Test|A unit test framework for QML applications, where the test cases are written as JavaScript functions.|
|Qt SQL|Classes for database integration using SQL.|
|Qt Test|Classes for unit testing Qt applications and libraries.|
|Qt Widgets|Classes to extend Qt GUI with C++ widgets.|

&nbsp; 

![0c](../assets/pics/qt_core.png)  

&nbsp; 

<a name="ch8-1-1"></a>
#### 8.1.1 Basic QML Concepts  

```js
Image {
    id: root
    ...
    Image {
        id: pole
        anchors.horizontalCenter: parent.horizontalCenter
        anchors.bottom: parent.bottom
        source: "images/pole.png"
    }

    Image {
        id: wheel
        anchors.centerIn: parent
        source: "images/pinwheel.png"
    }
    ...
}
```

Placing an image as a child type of our root type (the *Image*) illustrates an important concept of a declarative language. You describe the visual appearance of the user interface in the order of layers and grouping, where the topmost layer (our background image) is drawn first and the child layers are drawn on top of it in the local coordinate system of the containing type.  

```
Image {
    id: root
    ...
    MouseArea {
        anchors.fill: parent
        onClicked: wheel.rotation += 90
    }
    ...
}
```

The mouse area emits signals when the user clicks inside the area it covers. You can connect to this signal by overriding the *onClicked* function.  

This technique works for every signal, with the naming convention being  
```js
on + SignalName
```


Also, all properties emit a signal when their value changes. For these signals, the naming convention is:
```js
on + PropertyName + Changed
```

For example, if a width property is changed, you can observe it with ``onWidthChanged: print(width)``.  

&nbsp; 

<a name="ch8-1-2"></a>
#### 8.1.2 Properties  
Elements are declared by using their element name but are defined by using their properties or by creating custom properties. A property is a simple key-value pair, e.g. *width : 100*, *text: 'Greetings'*, *color: '#FF0000'*. A property has a well-defined type and can have an initial value.  

```js
Text {
    // (1) identifier
    id: thisLabel

    // (2) set x- and y-position
    x: 24; y: 16

    // (3) bind height to 2 * width
    height: 2 * width

    // (4) custom property
    property int times: 24

    // (5) property alias
    property alias anotherTimes: thisLabel.times

    // (6) set text appended by value
    text: "Greetings " + times

    // (7) font is a grouped property
    font.family: "Ubuntu"
    font.pixelSize: 24

    // (8) KeyNavigation is an attached property
    KeyNavigation.tab: otherLabel

    // (9) signal handler for property changes
    onHeightChanged: console.log('height:', height)

    // focus is need to receive key events
    focus: true

    // change color based on focus value
    color: focus?"red":"black"
}
```

Let’s go through the different features of properties:  

1. *id* is a very special property-like value, it is used to reference elements inside a QML file (called “document” in QML). The *id* is not a string type but rather an identifier and part of the QML syntax. An *id* needs to be unique inside a document and it can’t be reset to a different value, nor may it be queried. (It behaves much like a reference in the C++ world.)  
&nbsp; 
2. A property can be set to a value, depending on its type. If no value is given for a property, an initial value will be chosen. You need to consult the documentation of the particular element for more information about the initial value of a property.  
&nbsp; 
3. A property can depend on one or many other properties. This is called binding. A bound property is updated when its dependent properties change. It works like a contract, in this case, the *height* should always be two times the *width*.  
&nbsp; 
4. Adding own properties to an element is done using the *property* qualifier followed by the type, the name and the optional initial value (*property \<type\> \<name\> : \<value\>*). If no initial value is given a system initial value is chosen.  
&nbsp; 
5. Another important way of declaring properties is using the *alias* keyword (*property alias \<name\>: \<reference\>*). The *alias* keyword allows us to forward a property of an object or an object itself from within the type to an outer scope. We will use this technique later when defining components to export the inner properties or element ids to the root level. A property alias does not need a type, it uses the type of the referenced property or object.  
&nbsp; 
6. The *text* property depends on the custom property *times* of type int. The *int* based value is automatically converted to a *string* type. The expression itself is another example of binding and results in the text being updated every time the *times* property changes.  
&nbsp; 
7. Some properties are grouped properties. This feature is used when a property is more structured and related properties should be grouped together. Another way of writing grouped properties is *font { family: "Ubuntu"; pixelSize: 24 }*.  
&nbsp; 
8. Some properties are attached to the element itself. This is done for global relevant elements which appear only once in the application (e.g. keyboard input). The writing is *\<Element\>.\<property\>: \<value\>*.  
&nbsp; 
9. For every property, you can provide a signal handler. This handler is called after the property changes. For example, here we want to be notified whenever the height changes and use the built-in console to log a message to the system.  
&nbsp; 

You can also declare one property to be the default property if no property name is given by prepending the property declaration with the *default* keyword. This is used for example when you add child elements, the child elements are added automatically to the default property *children* of type list if they are visible elements.  

&nbsp; 

**Property Aliases**  
Unlike a property definition, which allocates a new, unique storage space for the property, a property alias connects the newly declared property, called the aliasing property as a direct reference to an existing property, the aliased property. Read or write operations on the aliasing property results in a read or write operations on the aliased property, respectively.  

A property alias declaration is similar to an ordinary property definition:  

``[default] property alias <name>: <alias reference>``  

As the aliasing property has the same type as the aliased property, an explicit type is omitted, and the special *alias* keyword is before the property name. Instead of a default value, a property alias has a compulsory alias reference. Accessing the aliasing property is similar to accessing a regular property. In addition, the optional default keyword indicates that the aliasing property is a default property.  

```js
property alias buttonLabel: label.text
Text {
    id: label
    text: "empty label"
}
```  

When importing the component as a *Button*, the *buttonlabel* is directly accessible through the *label* property.  

```js
Button {
    id: textbutton
    buttonLabel: "Click Me!"
}
```  

In addition, the *id* property may also be aliased and referred outside the component.  

```js
Rectangle {
    property alias buttonImage: image

    Image {id: image}
}
```  

The *imagebutton* component has the ability to modify the child Image object and its properties.

```js
Button {
    id: imagebutton
    buttonImage.source: "http://qt.nokia.com/logo.png"
    buttonLabel: buttonImage.source
}
```  

&nbsp; 

> Using aliases, properties may be exposed to the top level component. Exposing properties to the top-level component allows components to have interfaces similar to Qt widgets.  

> (!) Aliases are only activated once the component completes its initialization. An error is generated when an uninitialized alias is referenced. Likewise, aliasing an aliasing property will also result in an error.



&nbsp; 

<a name="ch8-2"></a>
### 8.2 Basics  
 
````c
#include <QApplication>
#include <QLabel>

int main (int argc, char **argv) {
  QApplication app(argc, argv);
  QLabel l("Hello World!");
  l.show();
  return app.exec();
}
````

**QApplication**  
Jede Applikation enthält genau eine (!) Instanz dieser Klasse. Sie hält das Ganze zusammen und bewerkstelligt die Kommunikation zwischen Benutzer und den Objekten. Wichtig: am Ende der Main-Methode der *exec()* - Aufruf.  

**QObject**  
QObject ist die Basisklasse von nahezu allen QT-Klassen und allen Widgets. Sie enthält viele der Machanismen die Qt ausmachen, z.b. Events, *Signals&Slots* oder Speichermanagement.  

**QWidget**  
abgeleitet von der 'Urklasse' *QObject*, stellt eine Instanz der Klasse QWidget ein grafisches Element dar. Die Klasse Widget bringt viele der Methoden mit, um das Aussehen, Größe, Position auf dem Bildschirm, etc. zu verändern. Mit *show()* wird das Widget angezeigt, mit *hide()* versteckt. Jedes Widget wird innerhalb dessen Vater-Widgets dargestellt.  

&nbsp;

**[Meta Data]**  
- Qt implements introspection in C++  
    - every QObject has a meta object
    - the meta object knows about  
        - class name (QObject::className)
        - inheritance (QObject::inherits)
        - properties
        - signals and slots
        - general information (QObject::classInfo)
- The meta data is gathered at compile time by the *meta object compiler* (moc)
- The *moc* harvests data from the header  

&nbsp;

![emu](../assets/pics/mocs_qt.png)  

&nbsp;

- What does *moc* look for?


[Back](../)
