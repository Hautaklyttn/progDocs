---
layout: default
---

[Back](../)

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


&nbsp;

[Back](../)
