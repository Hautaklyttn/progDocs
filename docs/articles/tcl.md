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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.2 Packages](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.3 Regular Expressions](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.4 `scan` command](#ch1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.5 `binary scan` command](#ch1-5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [1.6 `VARIANT` data type](#ch1-6)

### 2. Tcl - Tk
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.1 Fenster aufsetzen](#ch2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.2 Funktionalität hinter Menüpunkt](#ch2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.3 Unterdrückung des leeren `wish`-Fensters](#ch2-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2.4 `grid` Layout Manager](#ch2-4)

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

&nbsp;

<a name="ch1-2"></a>
### 1.2 Packages  
**1.2.1 Einbinden eines Packages**  
(1) Erstellen des Packages mit Zeile `package provide <package_name>`  
(2) Hinzufügen des neuen Package in (neues oder bestehendes) "pkgIndex.tcl" File:  
```js  
package ifneeded <package_name> <version> [list source [file join $dir <directory>]]  
```
(3) Die globale Variable "auto_path" sammelt alle Pfade in denen sich die pkgIndex.tcl (und damit die Packages) befinden können.  
(4) Nutzen eines Packages indem man im jeweiligen File die Zeile `package require <package_name> <version>` einfügt.  

Nützliche Kommandos:  
  a) ``package names``: Listet alle geladenen Packages auf  
  b) ``Log $auto_path``: Gibt alle gelisteten Verzeichnisse aus  

> 'tcllib' runterladen! Enthält zusätzliche Packages die nicht im Standard-Interpreter enthalten sind.  

&nbsp;

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

```  
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

<a name="ch1-5"></a>
### 1.5 `binary scan` command  

```  
binary scan <string> <formatString> ?varName varName ...?  
```  
Extracts data from a binary string and returns it as ordinary Tcl string values. Return value is the number of conversions performed. *\<string\>* gives the input to be parsed and *\<formatString\>* indicates how to parse it. When a field is scanned from *\<string\>*, the result is assigned to the corresponding variable in *\<varName\>*.  

```js
binary scan \x01\x02\x03\x04 x2H* var1
    // Rückgabewert: '1'
    // var1 = '0304'
```

`x` - moves the cursor forward 'count' bytes in *\<string\>* (hier: 2). If 'count' is '\*' or is larger than the number of bytes after the current cursor position, then the cursor is positioned after the last byte in *\<string\>*. If 'count' is omitted, then the cursor is moved forward one byte.

`H` - data is turned into a string of 'count' (hier: \*) hexadecimal digits in high-to-low order within each byte. The data bytes are scanned in first to last order. Any extra bits in the last byte are ignored. If 'count' is '\*', then all of the remaining hex digits in *\<string\>* will be scanned. If 'count' is omitted, then one hex digit will be scanned.  

'count' := number after the indicator (x<u>2</u>H<u>\*</u>)

&nbsp;

<a name="ch1-5"></a>
### 1.6 `VARIANT` data type  
Variables in **VisualBasic (VBA)** tend to be of type "variant".  

To construct a variable in Tcl of type "variant" (with subtype <type>) the following needs to be done:  
```js
::tcom ::variant <type> <data>
```  
*\<type\>* is: 'bstr', 'error', 'bool', 'variant', 'decimal', 'i1', 'ui1', 'ui2', 'ui4', 'i8', 'ui8', int, 'uint'  
*\<data\>* is the data to be converted. 

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

<a name="ch2-4"></a>
### 2.4 `grid` Layout Manager  
'grid' geht von einem "Schachbrettmuster" aus auf dem die einzelnen "widgets" verteilt werden. Die Größe der Felder hängt von der Höhe/Breite der genutzten widgets ab.  

Optionen:  
`-column <n>  /  -row <n>`  
Insert the widget in the n-th column/row (starting from 0)  

`-columnspan <n>  /  -rowspan <n>`  
Arrange for the widget to span n clumns/rows. Default is one column/row.  

`padx <n>  / pady <n>`  
Horizontal ('x') <u>external</u> padding and Vertical ('y') <u>external</u> padding  

`ipadx <n>  / ipady <n>`  
Horizontal ('x') <u>internal</u> padding and Vertical ('y') <u>internal</u> padding  

`-sticky <side(s)>`  
How the widget should be positioned and stretched within its cell. *\<side(s)\>* contains one or more of the character n,s,e or w. Each letter refers to the side to which the widget will stick.  

`rowconfigure <master> <index> <option value>`  
(&rarr; same for 'columnfigure')  
Set the row properties of the <index> row in <master>. Valid option are:  
   - `-pad <amount>`: Units in padding on the top and bottom of the tallest window in row  
   - `-weight <int>`: Every row (and column) has a 'weight' grid option associated with it, which tells it how much it should grow if there is extra room in the <master> to fill. By default, the 'weight' of each column or row is '0' meaning don't expand to fill space.

> "grid" and "place" lassen sich kombinieren!

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
