---
layout: default
---

[Back](../)  

&nbsp;

# Tcl
---  

&nbsp;

### 1. Basics    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 Tcl Interpreter</font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 Packages</font>](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3 Regular Expressions</font>](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.4 `VARIANT` data type</font>](#ch1-6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.5 ...</font>](#ch1-7)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.6 ...</font>](#ch1-8)  

### 2. Tcl - Tk
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Fenster aufsetzen</font>](#ch2-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.2 Funktionalität hinter Menüpunkt</font>](#ch2-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.3 Unterdrückung des leeren `wish`-Fensters</font>](#ch2-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.4 `grid` Layout Manager</font>](#ch2-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.5 Darstellung dynamischer Daten (2D-Plot)</font>](#ch2-5)  

### 3. Functions  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 `scan` command</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 `binary scan` command</font>](#ch3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.3 Befehle für Tcl-Programm-Interna</font>](#ch3-3)  

### 4. HowTo's  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.1 Konsolenfenster manuell öffnen</font>](#ch4-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.2 Windows-Prozesse beenden</font>](#ch4-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.3 .zip compression</font>](#ch4-3)  

### 5. IPG CarMaker
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.1 Basics</font>](#ch5-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.2 XCP</font>](#ch5-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.3 CarMaker-interne Funktion verändern</font>](#ch5-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.4 CM Namespace ::Appl</font>](#ch5-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">5.5 CM Namespace ::TestMgr</font>](#ch5-5)  

### 6. Incr Tcl    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.1 Fundamental Expressions</font>](#ch6-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">6.2 ...</font>](#ch6-2)  

&nbsp;

---  
&nbsp;


# Basics  

<a name="ch1-1"></a>
### 1.1 Tcl Interpreter  

**1.1.1 System Startup / Interpreter Files**  
1. `init.tcl` (in "lib/tcl8.6")  
The main file sourced by a Tcl interpreter when starting up (during 'Tcl_init'). When Tcl starts up, it searches for a directory that contains its 'init.tcl' startup script. You can short-circuit the search by defining the 'TCL_LIBRARY' environment variable (not needed in Tcl 8.0.5 or later).  
The primary thing defined by 'init.tcl' is the implementation of the 'unknown' procedure. It also initializes 'auto_path' to contain '$tcl_library' and the parent directory added to 'auto_path' depending on the compiled in value of 'tcl_pkgPath'.  

2. `auto_path` variable  
Contains a valid Tcl list giving directories to search during auto-load operations. Variable is initialized during startup. Additional locations to look for files and packages indices should normally be added to this variable using 'lappend'. 'auto_path' init settings are set in 'init.tcl'. To add initial paths, one can set the environment variable 'TCLLIBPATH'. The following code can be added therefore in 'init.tcl':  
```js
if {[info exists env(TCLLIBPATH)]} {set env(TCLLIBPATH) [list <path>]}
```

3. `env` variable  
This variable is maintained by Tcl as an array whose elements are the environment variables for the process.  
   - **env(HOME)**  
   This environment variable, if set, gives the location of the directory considered to be the current user's home directory.  
   - **env(TCL_LIBRARY)**  
   If set, then it specifies the location of the directory containing library scripts (the value of this variable will be assigned to the 'tcl_library' variable and therefore returned by the command ``[info library]``)  
   - **env(TCLLIBPATH)**  
   If set, then it must contain a valid Tcl list giving directories to search during auto-load operations. Directories must be specified in Tcl format, using "/" as path seperator, regardless of platform. This variable is only used when initializing the "auto_path" variable.

&nbsp;

**1.1.2 Action-Oriented vs. Object-Oriented**  
In Tcl there are two approaches when defining commands in an application.
> In the **action-oriented approach** there is one command for each action that can be taken on an object, and the command takes an object name as an argument. For example Tcl's file commands are action-oriented: there are separate commands for opening files, reading, writing, closing, etc.  
In the **object-oriented approach** there is one command for each object, and the name of the command is the name of the object. When the command is invoked its first argument specifies the operation to perform on the object. Tk's widget work this way: if there is a button widget .b, there is also a command named .b you can invoke: '.b flash' to flash the widget or '.b invoke' to evaluate its Tcl script.  
The action-oriented approach works well when there are many objects or the objects are unpredictable or short-lived.  
The object-oriented approach works well when the number of objects isn't too great and the objects are well defined and exist for at least moderate amounts of time. The object-oriented approach has the advantage that it doesn't pollute the command name space with lots of commands for individual actions.

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
### 1.4 `VARIANT` data type  
Variables in **VisualBasic (VBA)** tend to be of type "variant".  

To construct a variable in Tcl of type "variant" (with subtype <type>) the following needs to be done:  
```js
::tcom::variant <type> <data>
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
set w . <window_name>             // Aufsetzen Fenster (Name: <window_name>)
toplevel $w   
wm title $w "<name_title>"        // Name des Fensters in Titelzeile
wm geometry $w 300x200+300+300    // Fenster-Größe und Fenster-Startposition

wm resizable $w 0 0               // feste Fenstergröße
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

> "grid" und "place" lassen sich kombinieren!

&nbsp;  

<a name="ch2-5"></a>
### 2.5 Darstellung dynamischer Daten (2D-Plot)  

1. Möglichkeit: `canvas` - widget  
Funktion `xview scroll <number> <what>` gibt die Möglichkeit einer scrollenden Darstellungsfläche (z.B. ``.c xview scroll 1 unit``). Probleme bei sehr dynamischen Charts: Canvas erzeugt keine Linien mehr zwischen den Punkten (&rarr; Unbrauchbar).  

2. Möglichkeit: `vector`/`strip-chart` in BLT  
Veränderung in einer 'Vector'-Variable wird automatisch in einem Graph, der diese Werte enthält, übernommen. D.h. in die Lap muss nur die Neuberechnung der 'Vector'-Punkte, nicht das Zeichnen des 'strip-charts' selber,´.  
'Strip-chart' hat bereits alle nötigen Features integriert (parametrierbares 2D-Chart, parametrierbare Axen, parametrierbare Legende, usw.). Ist in der Lage auch hochdynamische Daten dazustellen (über Vektoren).

&nbsp;  

# Functions  

<a name="ch3-1"></a>
### 3.1 `scan` command  

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

<a name="ch3-2"></a>
### 3.2 `binary scan` command  

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

<a name="ch3-3"></a>
### 3.3 Befehle für Tcl-Programm-Interna  
- `namespace children <namespace>`  
Gibt eine Liste aller Unter-Namespaces zurück  

- `info proc <namespace>::*`  
Gibt eine Liste aller proc's im <namespace> zurück  

- `info body <namespace>::<proc>`  
Gibt den proc-Körper (=Code) zurück  

- `info args <namespace>::<proc>`  
Gibt die Argumente von \<proc\> zurück  

- `info vars <namespace>::*`  
Gibt eine Liste aller Variablen im <namespace> zurück   

&nbsp;

# HowTo's  

<a name="ch4-1"></a>
### 4.1 Konsolenfenster manuell öffnen  
```js
catch {console show}
```  
Befehl öffnet ein eigenes Konsolenfenster in dem alle getätigten Ausgaben erscheinen (z.B. per "puts").

&nbsp;

<a name="ch4-2"></a>
### 4.2 Windows-Prozesse beenden
  - Liste aller aktiven COM-Objekte:
    ```js
    info commands ::tcom::handle*
    ```
  - Liste aller PID's (process Id's) in Windows (twapi package):
    ```js
    twapi::get_process_ids
    ```  
  - Abfragen, welches Programm zur jew. PID gehört:  
    ```js
    exec {*}[auto_execok tasklist] /fi "pid eq <pid_no>"      // <pid_no> ist Integer
    ```    
  - Prozesse beenden:
    - über PID:
      ```js
      exec [auto_execok taskkill] /PID $pid
      ```     
    - über PID (twapi):
      ```js
      twapi::end_process -force $pid
      ```       
    - **Best Use:** über Name:
      ```js
      exec {*}[auto_execok taskkill] /IM "Excel.exe" /T /F
      ```    
      **/T** = kills child process, **/F** = forceful termination

&nbsp;

<a name="ch4-3"></a>
### 4.3 .zip compression

Simplest way to create a .zip-archive is to call the program "7-zip" with the command `eval exec`.  

```
eval exec -- <path/to/7z.exe> a -tzip <path/to/targetfile> <path/to/file2zip>
```  

**<path/to/targetfile>** : Path and file name (with .zip extension) to the target .zip file  
**<path/to/file2zip>** : Path and file or directory which is supposed to be zipped

&nbsp;

# IPG CarMaker  

<a name="ch5-1"></a>
### 5.1 Basics

&nbsp;

<a name="ch5-2"></a>
### 5.2 XCP

1. Einstellungen unter `Realtime System` &rarr; `XCP Configuration`
2. Dort werden benötigte ASAP's einer Gruppe ("Sample Group") zugeordnet. "Sample Rate" auf 10ms setzen und dahinter den Haken setzen, anschließend speichern.  
3. Rechts-Klick im Fenster unten auf "Connect" klicken. Erscheint kein Fehler, sollte Verbindung funktionieren. Zusätzlicher  Test durch Rechts-Klick und "Start DAQ" möglich. Es sollte Messung starten, Stoppen der Messung mit "Stop DAQ".

&nbsp;

<a name="ch5-3"></a>
### 5.3 CarMaker-interne Funktion verändern  

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

<a name="ch5-4"></a>
### 5.4 CM Namespace ::Appl  

#### 5.4.1 *proc* Übersicht  

|proc|Beschreibung|  
|:---|:---|
|::SelectExe|Abhängig vom Array 'Pgm()'-Inhalt, wird die richtige Exe (bei HiL: .xeno) für das System gewählt|  
|::Disconnect|Trennt CM vom HiL (=> 'Disconnect' button)|  
|::Reboot|Neu booten des HiL Systems (=> 'Reboot' button)|  
|::Shutdown|Fährt das HiL-Sytem runter (=> 'Shutdown System' button)|  
|::Popup|Code, der die GUI ``Application Configuration`` schreibt. (!) Gute Quelle für hinterlegtes Verhalten|  
|::Terminate|Beendet laufendes Simulationsprogramm *²|  
|::ArchStr|Gibt bei Aufruf einen String zurück, der das jeweilige System angibt (z.B. 'Office' für SiL, 'xeno' für HiL)|  
|::Connect|Verbindet HiL mit CM (=> 'Connect' button)|  
|::Update|Proc updatet den 'ApplicationStatus'-Tab im 'ApplicationConfiguration'-Fenster|  
|::IPGRTHost|Gibt einen String zurück, der den jeweiligen HiL-Namen angibt ('SimX..')|  
|::Start|Funktionalität hinter `Start&Connect`|  
|::CMDir|Gibt den Pfad zurück, von wo aus die aktuelle HiL-Exe gestartet wurde|  

\*² : Funktion hinter `Terminate Application` button:
```
Appl::SilentConnect
Appl::Terminate 1
```

&nbsp;

<a name="ch5-5"></a>
### 5.5 CM Namespace ::TestMgr  

#### 5.5.1 *proc* Übersicht  

|proc|Beschreibung|  
|:---|:---|
|::GetResult|Liefert das aktuelle Test-Resultat zurück ('good', 'bad', etc).|  
|::SetResult \<res\>|Setzt aktiv das Resultat des TestRuns auf \<res\>|  
|::SkipToEnd \<kind\>|Macht es möglich ans Ende von \<kind\> zu springen (\<kind\> = TestSeries, Group, TestRunGroup oder TestRun)|  
|::DoSetting \<name\> \<type\> \<val\>|Setzt Werte vom Typ \<type\> (z.B. KValue, NValue) mit Namen \<name\> und Wert \<val\>|  
|::Save \<file\>|Speichert \<file\> im angegebenen Pfad|  
|::Load \<file\>|Lädt \<file\> aus angegebenen Pfad|  
|::ClearResults|Löscht alle Test-Resultate aus aktuellem TestManager file|  
|::PopUp|Enthält den Code der das 'TestManager'-Fenster erstellt mit allen Inhalten|  
|::Start|dem `Start` button hinterlegter Code|  
|::Stop|dem `Stop` button hinterlegter Code|  
|::New|dem `New` button hinterlegter Code|  
|::ClearTS|Löscht den Inhalt des namespace ::TS|  

#### 5.5.2 *var* Übersicht  

|var|Beschreibung|  
|:---|:---|
|::FName|Gibt das aktuell geladene TS file zurück|  
|::Data|Enthält den Inhalt des TS files als dictionary|  
|::TestRunFName|Gibt den Namen des zuletzt gefahrenen TestRun zurück|  
|::tc|Ist der String 'tm.tc' hinterlegt. Hieraus lassen sich Befehle erstellen, die direkt auf (aktuelle, dynamische) Inhalte des TestManagers zugreifen:|
||**$TestMgr::tc selection get** : Gibt den aktuell ausgewählten, d.h. blau hinterlegten Punkt (als Zeilennummer) im TestManager Fenster zurück.|  
||**$TestMgr::tc item text \<zeilennummer\>** : Gibt Infos zur \<zeilennummer\>-Zeile zurück (Text in Zeile, Zeilennummer, u.a.).|  
||**$TestMgr::tc item parent \<zeilennummer\>** : Gibt die Zeilennummer des zu Zeile \<zeilennummer\> übergeordneten Elementes zurück.|  
||**$TestMgr::tc selection clear** : Entfernt alle ausgewählten (d.h. blau hinterlegten) Punkte im 'Test-Manager'-Fenster.|  
||**$TestMgr::tc selection add \<zeilennummer\>** : Fügt an der Stelle \<zeilennummer\> eine Auswahl hinzu (blau hinterlegter Punkt).|  
|::Result|Enthält das letzte Resultat ('good', 'bad', etc.).|  
|::LastChange|Gibt Datum/Uhrzeit/Nutzer bei letzter Änderung des TS files an.|  
|::tw|Ist der String '.tm' hinterlegt (= handle für 'TestManager'-Fenster)|  

&nbsp;

# Incr Tcl  

<a name="ch6-1"></a>
### 6.1 Fundamental Expressions  

```
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
