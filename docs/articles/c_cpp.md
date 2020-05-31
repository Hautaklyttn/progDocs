---
layout: default
---

[Back](../)

&nbsp;

# C und C++
---

&nbsp;

# Basics

&nbsp;

### Eigenschaften von C

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

### C und C++

C++ ist eine Weiterentwicklung von C. C++ wurde entworfen, um zusätzlich zum klassischen C-Programmierstil  
- ein objektorientiertes Programmieren zu unterstützen  
- und ein **strenges Typkonzept für selbst definierte Datentypen. die Klassen**, zu realisieren, bei dem für einen Datentyp nur definierte Operationen zulässig sind. Hierbei darf der Compiler nur sehr eingeschränkte implizite Typwandlungen durchführen, ansonsten muss er Typverletzungen anzeigen.  

Während C als "Super-Assembler" für hardwarenahe Software entwickelt wurde, liegt die Zielrichtung bei der Entwicklung von C++ darin, dem Programmierer neue Sprachmittel wie z.B. Klassen in die Hand zu geben, um die Anwendungsprobleme zu formulieren.  

Der ANSI-C Standard revidierte ursprüngliche Inkompatibilitäten von C und C++, so dass C++ so nahe an C ist wie möglich. Eine hundertprozentige Kompatibilität ist jedoch nicht das Ziel, weil C++ eine höhere Typsicherheit anstrebt als C.  

&nbsp;

![01](../assets/pics/stammbaum.png)  
C in der Verwandschaftstafel höherer Programmiersprachen  

&nbsp;

### Auswertungsreihenfolge  

Wie in der Mathematik spielt es bei C eine wichtige Rolle, in welcher Reihenfolge ein Ausdruck berechnet wird.  

1. Wie in der Mathematik werden als erstes **Teilausdrücke in Klammern** ausgewertet.  
2. Dann werden **Ausdrücke mit unären Operatoren** ausgewertet.  
   Unäre Operatoren werden von rechts nach links angewendet. Dies bedeutet, dass  
      2.1 zuerst die **Postfix-Operatoren** auf ihre Operanden  
      2.2 und dann die **Präfix-Operanden** auf ihre Operanden angewendet werden  
3. Anschließend werden Teilausdrücke mit **mehrstelligen Operatoren** ausgewertet

&nbsp;

# Arrays  

In C gibt es im Gegensatz zu anderen Sprachen **kein Schlüsselwort array**. Der C-Compiler erkennt ein Array an den eckigen Klammern, die bei der Definition die Anzahl der Elemente enthalten. Die **Anzahl der Elemente** muss immer eine positive ganze Zahl sein. Sie kann gegeben sein durch eine Konstante oder einen konstanten Ausdruck, **nicht aber durch eine Variable**. Dies bedeutet, dass die Größe nicht dynamisch zugeordnet werden kann. Dennoch können Arrays mit einer zur Laufzeit berechneten Größe mit Hilfe der Funktion `malloc()` oder `calloc()` konstruiert werden.  
&nbsp;

> Eine tückische Besonderheit von Arrays in C ist, dass beim Überschreiten des zulässigen Indexbereiches kein Kompilier- bzw. Laufzeitfehler erzeugt wird. So würde bei einem Array `int alpha[5]` die Anweisung `alpha[5] = 6` einfach die Speicherzelle direkt nach `alpha[4]` mit dem Wert 6 überschreiben.  


> Auf jeden Fall sollte man es sich bei Arrays zur Gewohnheit machen, immer mit symbolischen Konstanten wie z.B. `#define MAX 40` und nie mit literalen Konstanten wie z.B. `int fahrenheit [40]` zu arbeiten. Soll nämlich der Wert in einer nächsten Version des Programms bis 100 Grad Celsius betragen, so müsste man doch  an vielen Stellen (z.B. in den Eingabeauforderungen und in den Kommentaren) Änderungen vornehmen, von denen leider gerne welche vergessen werden.



&nbsp;

[Back](../)
