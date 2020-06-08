---
layout: default
---

[Back](../)  

&nbsp;

# Tcl
---  

&nbsp;

## Overview

### 1. Basics    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.1 ...](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.2 ...](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.3 Regular Expressions](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.4 `scan` command](#ch1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.5 `binary scan` command](#ch1-5)  

### 2. Tcl - Tk
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.1 Fenster aufsetzen](#ch2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.2 Funktionalität hinter Menüpunkt](#ch2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.3 Unterdrückung des leeren `wish`-Fensters](#ch2-3)  


### 3. IPG CarMaker
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [3.1 Basics](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [3.2 XCP](#ch3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [3.3 CarMaker-interne Funktion verändern](#ch3-3)  

### 4. Incr Tcl    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [4.1 Fundamental Expressions](#ch4-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [4.2 ...](#ch4-2)  

&nbsp;

---  
&nbsp;


# Basics  

### 1.1 ...  

### 1.2 ...  

<a name="ch1-3"></a>
### 1.3 Regular Expressions  

``^`` (called 'anchor') is used to search for pattern at the beginning of a string  
``$`` (called 'dollar') is used to search for pattern at the end of a string  

To search for the exact pattern *\<pattern\>* in a string use the following command   
```js
regexp {^<pattern>$}
```
If the string contains other characters, the return value is 0.

`[]` are used to specify a range in search patterns  
`+` symbol indicated the range specified in [] to occur 1 or more times  

E.g. to look for small alphabetical characters in the string stored in variable e, type
```js
regexp {[a-z]+ $e}

// Other search patterns
regexp {\d+} $e     // searches for digits
regexp {\D+} $e     // searches for not digits
regexp {\s+} $e     // searches for spaces
regexp {\S+} $e     // searches for not spaces
```

&nbsp;

<a name="ch1-4"></a>
### 1.4 `scan` command  

```js  
scan <string> <format> <varName> ?varName?  
```  

This command parses substrings from an input string *\<string\>* in a fashion similar to the ANSI C **sscanf** procedure and returns a count of the number of conversions performed. *\<string\>* gives the input to be parsed and *\<format\>* indicates how to parse it, using ``%`` as a conversion specifier. Each *\<varName\>* gives the name of a variable; when a field is scanned from *\<string\>*, the result is converted back into a string and assigned to the corresponding variable.  
When a '%' is encountered in *\<format\>*, it indicates the start of a conversion specifier. It converts the next input character according to the conversion specifier and stores the result in the variable given by the next argument to 'scan'.

The following "conversion characters" are supported (and more):  
`d` - The input field must be a decimal integer. It is read in and the value is stored in the variable as a decimal string.  
`o` - The input field must be an octal integer. It is read in and the value is stored in the variable as a decimal string.  
`x` - The input field must be a hexadecimal integer. Read in and stored in variable as a decimal string.  
`c` - A single character is read in and its binary value is stored in the variable as a decimal string.  

&nbsp;

<a name="ch1-4"></a>
### 1.5 `binary scan` command  

```js  
binary scan <string> <formatString> ?varName varName ...?  
```  
Extracts data from a binary string and returns it as ordinary Tcl string values. Return value is the number of conversions performed. *\<string\>* gives the input to be parsed and *\<formatString\>* indicates how to parse it. When a field is scanned from *\<string\>*, the result is assigned to the corresponding variable in *\<varName\>*.


&nbsp;


# Tcl - Tk
<font size="+2">- Grafische Anwendungsprogrammierung -</font>  
&nbsp;

<a name="ch2-1"></a>
### 2.1 Fenster aufsetzen

```js   
set w . <window_name>               // Aufsetzen des Fensters mit Bezeichner <window_name>
toplevel $w   
wm title $w "<name_title>"          // Name des Fensters in Titelzeile
wm geometry $w 300x200+300+300      // Fenster-Größe und Fenster-Startposition

wm resizable $w 0 0                 // feste Fenstergröße
```

&nbsp;

<a name="ch2-2"></a>
### 2.2 Funktionalität hinter Menüpunkt

z.B `.mbar.rts.m entrycget 4 -command`  (am Beispiel IPG CarMaker)  
liefert die Funktion die im DropDown-Menü "Realtime System" an vierter Stelle hinterlegt ist.  

&nbsp;  

<a name="ch2-3"></a>
### 2.3 Unterdrückung des leeren `wish`-Fensters  

Starten des Skripts mit
```c
wm withdraw .
```
schließt das leere 'wish'-Fenster.

&nbsp;  


# IPG CarMaker  

<a name="ch3-1"></a>
### 3.1 Basics

&nbsp;

<a name="ch3-2"></a>
### 3.2 XCP

1. Einstellungen unter `Realtime System` &rarr; `XCP Configuration`
2. Dort werden benötigte ASAP's einer Gruppe ("Sample Group") zugeordnet. "Sample Rate" auf 10ms setzen und dahinter den Haken setzen, anschließend speichern.  
3. Rechts-Klick im Fenster unten auf "Connect" klicken. Erscheint kein Fehler, sollte Verbindung funktionieren. Zusätzlicher  Test durch Rechts-Klick und "Start DAQ" möglich. Es sollte Messung starten, Stoppen der Messung mit "Stop DAQ".

&nbsp;

<a name="ch3-3"></a>
### 3.3 CarMaker-interne Funktion verändern  

Funktion/proc: `PatchProc`  

```js
PatchProc <CarMaker_Func> {<Code-Zeile aus CarMaker_Func>} {<eigener Code>}
               (1)                     (2)                      (3)
```
(1) CarMaker-internes Programm, dem eigener Code hinzugefügt werden sollte  
(2) Code-Zeile im CarMaker-Programm, die anzeigt, wo eigener Code hinzugefügt werden soll  
(3) Eigener Code: meist ein selbst erstelltes 'proc', das aufgerufen werden soll  

Der Aufruf der 'PatchProc'-Funktion steht dann in einem tcl-Skript, das mit 'source' in File `.CarMaker.tcl` aufgerufen wird.

&nbsp;

# Incr Tcl  

<a name="ch4-1"></a>
### 4.1 Fundamental Expressions  

```js
itcl_class <class_name> {
  inherit <base_class> ?base_class?  
  constructor args body  
  destructor body  
  method <name> args body  
  proc <name> args body  
  public <var_Name> ?init? ?config?  
  protected <var_name> ?init?  
  common <var_name> ?init?  
}
```


[Back](../)
