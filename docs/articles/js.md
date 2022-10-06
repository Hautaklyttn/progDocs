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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3 Data Types</font>](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3.1 Type Casting</font>](#ch1-3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.4 Variables</font>](#ch1-4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.4.1 'Undefined'</font>](#ch1-4-1)  

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
### 1.3 Data Types  

Every value in a programming language has a **type** that describes the data it contains. This determines how the language will interpret and use the value. The data type determines what values it can take and what it can do.  

JavaScript doesn’t have a *char* primitive data type, but it does have `strings`, and a char could be represented by a single-character string.  

JavaScript doesn’t differentiate between *integers* and *floats*. It just has a single primitive data type of `Number`.  

**Composite data types** are made up of primitive data types in a structured format. JavaScript has two main composite data types: `Arrays`  and `Objects`. Both of these composite data types are *mutable*, which means they can be updated after they’ve been created. Two other *composite data types* are `Set` and `Map`.  



&nbsp;

<a name="ch1-3-1"></a>
#### 1.3.1 Type Casting  

There’s a special operator called `typeof` that can be used to find out what data type a value is.

1. `typeof <operand>` : 'typeof' operator is used to return the data type of an operand
   ```js
   typeof 'hello'; 
   << 'string'
   typeof 10;
   << 'number'
   typeof true;
   << 'boolean'
   typeof { name: 'JavaScript' };
   << 'object'
   typeof [ 1, 2, 3 ]; // this is an array, it's also considered an object
   << 'object'
   typeof function(){ }; // this is an empty function
   << 'function'
   ```
   &nbsp;
2. Conversion to 'boolean'  
   ```js
   var b=1
   b=Boolean(b)
   ``` 
   &nbsp;
3. Conversion to 'string'  
   ```js
   var s=1
   s=String(s)
   ``` 
   &nbsp;
4. Conversion to 'string'  
   ```js
   var n=1
   n=Number(n)
   ``` 

&nbsp;

<a name="ch1-4"></a>
### 1.4 Variables  

JavaScript is a **weakly typed** language, so you don’t need to specify the type of a variable when you declare it. This might seem to be a benefit at first, although it can make debugging a program difficult when it isn’t clear what type a variable should be.  

JavaScript originally used the keyword `var` to declare all variables. More modern versions of JavaScript have introduced the keywords `const` and `let` — `const` to declare variables that can’t be reassigned to a new value, and `let` to declare variables that will change during the program. You might still see `var` used in some code examples, and it works in almost the same way as using `let`.

&nbsp;

<a name="ch1-4-1"></a>
#### 1.4.1 *Undefined*   

`undefined` is a primitive data type that JavaScript assigns to any variable that hasn’t been explicitly assigned a value. It’s  basically JavaScript’s way of saying “I can’t find a value for this”. For example, try declaring a new variable called `score` in the console, but don’t assign a value to it:  

```js
let score;
```

Now take a look at that variable. You’ll see that JavaScript has assigned it a
value of `undefined` :

```js
score;
<< undefined
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
