---
layout: default
---

[Back](../)

&nbsp;

# Javascript
---

&nbsp;

### 1. Basics    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 Geschichte</font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 Logging</font>](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3 Type Casting</font>](#ch1-3)  

### 2. Functions
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Basic Functions</font>](#ch2-1)  

### 3. HowTo's
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 Dynamic variable names</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 Key &rarr; Value / Array</font>](#ch3-2)  

&nbsp;

# Basics

&nbsp;

<a name="ch1-1"></a>
### 1.1 Geschichte  
*JavaScript* (kurz *JS*) ist eine Skriptsprache, die ursprünglich 1995 von Netscape für dynamische  HTML in Webbrowsern wurde, um Benutzerinteraktion auszuwerten, Inhalte zu verändern, nachzuladen oder zu generieren und so die Möglichkeiten von HTML und CSS zu erweitern. Heute findet JavaScript auch außerhalb von Browsern Anwendung, so etwa auf Servern und in Microcontrollern.  

Der als ECMA Script standardisierte Sprachkern von Javascript beschreibt eine dynamische typisierte, objektorierientierte, aber klassenlose Skriptsprache. Sie wird allen objektorientierten Programmierparadigmen unter anderem auf der Basis von Prototypen gerecht, deren Deklaration ab ECMAScript6 mit einer Syntax, ermöglicht wird, wie sie ähnlich auch bei klassenbasierten Programmiersprachen üblich ist. In JavaScript lässt sich je nach Bedarf objektorientiert, prozedural oder funktional programmieren.  

&nbsp;

<a name="ch1-2"></a>
### 1.2 Logging  
1. `console.log("...")` : z.B. `console.log("Out: "+variable)`  
   &nbsp;
2. `console.assert(...)` : To test an expression and print an optional message  
   &nbsp;
3. `console.error(...)` : Rote Errorausgabe
   `console.warn(...)` : Warnung-Ausgabe
   `console.info(...)` : Info-Ausgabe

&nbsp;

<a name="ch1-3"></a>
### 1.3 Type Casting  
1. `typeof <operand>` : 'typeof' operator is used to return the data type of an operand
   &nbsp;
2. Convert to 'boolean'  
   ```js
   var b=1
   b=Boolean(b)
   ``` 
   &nbsp;
3. Convert to 'string'  
   ```js
   var s=1
   s=String(s)
   ``` 
   &nbsp;
3. Convert to 'string'  
   ```js
   var n=1
   n=Number(n)
   ``` 

&nbsp;

# Functions

&nbsp;

<a name="ch2-1"></a>
## 2.1 Basic Functions  

&nbsp;


# How To's

<a name="ch3-1"></a>
## 3.1 Dynamic variable names  
In *JavaScript* there are two ways by which you can create dynamic variables:  
1. `eval` function  
   ```js
   var pagenumber = 1
   eval ("var text_" +pagenumber+ "=123;")  
   ```  
   &nbsp;
2.`window` object  
   ```js
   var pagenumber = 1
   window ["text_"+pagenumber]=123;  
   ```  

&nbsp;

<a name="ch3-2"></a>
## 3.2 Key &rarr; Value / Array  
```js
var obj = {}
obj['fred'] = {}  

if('fred' in obj) {}   // check for presence of 'fred'
if(obj.fred) {}        // also checks for presence of 'fred'
if(obj['fred']) {}        // also checks for presence of 'fred'

// following statements all work
obj['fred']['apples'] = 1
obj.fred.apples = 1
obj.['fred'].apples = 1
```


&nbsp;

[Back](../)
