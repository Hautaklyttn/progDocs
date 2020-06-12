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

### 2. Arrays
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Basics</font>](#ch2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.2 Übergabe von Arrays</font>](#ch2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3 Übergabe von Zeichenketten</font>](#ch2-3)  


### 3. Pointer
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 Referencing and Dereferencing</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 Addition und Subtraktion</font>](#ch3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.3 Call-by-Value</font>](#ch3-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.4 Call-by-Reference</font>](#ch3-4)  

### 4. Pointer und Arrays   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.1 Vergleich von char-Arrays und Pointern auf Zeichenketten</font>](#ch4-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.2 Das Schlüsselwort ``const`` bei Pointern und Arrays</font>](#ch4-2)  

### 5. Programmsyntax und -semantik   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.1 Der Bedingungsoperator `A ? B : C`</font>](#ch5-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.2 `switch - case`</font>](#ch5-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.3 Das Schlüsselwort `extern`</font>](#ch5-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.4 Das Schlüsselwort `static`</font>](#ch5-4)  

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

<a name="ch3-3"></a>
### 3.3 Call-by-Value  

In vielen Programmiersprachen werden im Normalfall Parameter an Funktionen mithilfe einer Kopie übergeben. Das wird als **call-by-value** bezeichnet. Das bedeutet, dass innerhalb der aufgerufenen Funktion mit der Kopie gearbeitet wird und sich Änderungen nicht auf den ursprünglichen Wert auswirken.

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
  1. Im Kontext einer Variablendeklaration innerhalb einer Funktion sagt dieses Schlüsselwort, dass diese **Variable auf einer festen Speicheradresse gespeichert wird**. Daraus ergibt sich die Möglichkeit, dass eine Funktion, die mit 'static'-Variablen arbeitet, beim nächsten Durchlauf die informationen erneut nutzt, die in der Variable gespeichert wurden (wie in einem Gedächtnis).  

  2. Auch vor Funktionen sowie Variablen außerhalb von Funktionen kann das Schlüsselwort 'static' stehen. Das bedeutet, dass auf die Funktion/Variable **nur in der Datei in der sie steht zugegriffen werden kann**.  

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

[Back](../)
