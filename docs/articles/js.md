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

### 3. Build-In Types  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 Arrays</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1.1 Common Methods</font>](#ch3-1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1.2 Multi-dimensional Arrays</font>](#ch3-1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 ...</font>](#ch3-2)  

### 4. HowTo's
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.1 Dynamic variable names</font>](#ch4-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">4.2 Key &rarr; Value / Array</font>](#ch4-2)  

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

# Build-In Types

<a name="ch3-1"></a>
## 3.1 Arrays  

**Composite data types** can be used to collect primitive values in a structured way. Programming languages use a variety of different data structures to store values, but one of the most common is an `Array`.  

To create an **array literal**, you simply write the values, separated by commas, inside a pair of square brackets:    

```js
const shopping = ['Apple', 'Banana', 'Cupcake'];
```

To access a specific value in an array, we write its position in the array in square brackets:  

```js
shopping[0];
<< 'Apple'
```

If an element in an array is empty, *undefined* is returned:  

```js
shopping[5]; // there's nothing at position 5
<< undefined
```

Every array has a *length* property that tells us how many items it contains:  

```js
shopping.length;
<< 3
```
Notice that *undefined* are also counted when calculating the length of the array.  

&nbsp;

**Spread Operator**  
The *spread operator* is an ellipsis of three dots *( ... )* placed in front of an array that sits inside another array. It spreads out all the elements of the array into separate values. If you think of an array as being like a box full of values, then the spread operator is the equivalent of emptying the contents of the box into another box.

Say we wanted to place all three elements from *arrayA* into a new array called *arrayB*. We might try doing something like this:  
```js
const arrayA = [1,2,3];
const arrayB = [arrayA];

arrayB.length;
<< 1
```
Unfortunately, all we’ve done is place the whole of *arrayA* into *arrayB*.

If we apply the *spread operator* to *arrayA* when it’s placed inside another array, *arrayC* , it will unpack all the elements out and treat them as three separate values:  

```js
const arrayC = [...arrayA];

arrayC.length;
<< 3
```

&nbsp;

<a name="ch3-1-1"></a>
### 3.1.1 Common Methods  

In JavaScript, all arrays are constructed from the global **Array** class. All array methods are stored in the **Array.prototype** object. This means that array methods are shared between array instances via *prototypal inheritance*.  


- `pop()`  
  The pop() method removes the last item from an array.
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.pop() // Dan
   names; // Zoe,Adam
  ```
- `push()`  
  The push() method adds a new value to the end of an array.
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.push("Kyle") // Zoe,Adam,Dan,Kyle
  ```  
- `shift()`  
  The shift() method removes the first item from an array.
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.shift() // Zoe
   names; // Adam,Dan
  ```  
- `unshift()`  
  The unshift() method adds a new value to the beginning of an array.
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.unshift("Kyle") // Kyle,Zoe,Adam,Dan
  ```    
- `toString()`  
  Converts an array into a string of comma-separated array values.
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.toString() // Zoe,Adam,Dan
  ```
- `join()`  
  Similar to toString(), but you can specify the separator.
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.join(" and ") // Zoe and Adam and Dan
  ```
- `concat()`  
  Create a new array by concatenating existing arrays.
  ```js
   let nums = [1, 2, 3]
   let nums2 = [4, 5, 6]
   let nums3 = [7, 8, 9]
   let concatArr = nums.concat(nums2, nums3)
   // [1, 2, 3, 4, 5, 6, 7, 8, 9]
  ```
- `splice()`  
  The splice() method can be used to add new items to an array.
  ```js
   let arr = ["Danny", "Joe"]
   arr.splice(1, 0, "Alice", "Amy")
   console.log(arr) // ['Danny', 'Alice', 'Amy', 'Joe']
  ```
  The first parameter (1) defines the index from where the new elements should be added (spliced in).  
  The second parameter (0) defines how many elements should be removed.
- `slice()`  
  slice() slices out a piece of an array, and returns it in a new array.
  ```js
   let arr = ["Danny", "Joe", "Amy"]
   let slice = arr.slice(1) // ['Joe', 'Amy']
  ```   
  Above, we are slicing from the element at index 1. slice() does not mutate the original array.  
  We can provide a start and end index to splice from (up to but not including end index):
  ```js
   let arr = ["Danny", "Joe", "Amy"]
   let slice = arr.slice(0, 2) // ['Danny', 'Joe']
  ```
- `indexOf()`  
  Find the first index that contains a certain value (searches from left to right).
  ```js
   let arr = ["Danny", "Joe", "Amy", "Joe"]
   let index = arr.indexOf("Joe") // 1
  ```  
- `lastIndexOf()`  
  Find the last index that contains a certain value (searches from right to left).
  ```js
   let arr = ["Danny", "Joe", "Amy", "Joe"]
   let index = arr.lastIndexOf("Joe") // 3
  ```  
- `toString()`  
  Converts an array into a string of comma-separated array values
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.toString() // Zoe,Adam,Dan
  ```  
- `toString()`  
  Converts an array into a string of comma-separated array values
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.toString() // Zoe,Adam,Dan
  ```  
- `toString()`  
  Converts an array into a string of comma-separated array values
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   let strNames = names.toString() // Zoe,Adam,Dan
  ```                 
&nbsp;

**Higher-order array methods**  
A higher-order function is a function that accepts functions as arguments, and/or returns a function. So, higher-order functions are functions that operate on other functions. In JavaScript, these methods are shared between array instances via prototypal inheritance from **Array.prototype**.  

- `forEach()`  
  The forEach() method is basically just a shorter way of writing `for(let i = 0; i < arr.length; i++) {...}`. It loops through the given array, and calls the given call-back function for each of the elements in the array.
  ```js
   let numbers = [1, 2, 3, 4]
   numbers.forEach(n => console.log(n))
   // 1
   // 2
   // 3
   // 4
  ```     
  The call-back passed to the forEach() function can accept any of the three arguments:
   - the item value
   - the item index
   - the array itself      
- `map()`  
  The map function takes in a call-back function as argument, and executes that function on each element of the array it is working on. It maps each of the return values of the call-back into a new array. It does not mutate the original array.
  ```js
   let numbers = [1, 2, 3, 4]
   // Double all numbers
   let doubledNumbers = numbers.map(n => n * 2) // [2, 4, 6, 8]
   // Only double numbers at odd indexes
   let doubledOddIndexNumbers = numbers.map((n, i) => {
   if (i % 2 === 1) return n * 2
   else return n
   }) // [1, 4, 3, 8]
  ```     
  The call-back passed to the map() function can accept any of the three arguments:
   - the item value
   - the item index
   - the array itself   
- `filter()`  
  The filter method is used to filter out array elements that fail a boolean test. Only elements that pass the test are allowed through into the new return array.
  ```js
   let articles = [
   { title: "PHP classes", author: "Danny Adams" },
   { title: "Python arrays", author: "Amy Sanders" },
   { title: "Arrays in PHP", author: "Danny Adams" },
   ]
   // Lets say the user searches for all articles with PHP in the title
   let PHPArticles = articles.filter(a => a.title.includes("PHP"))
   // [
   //   { title: 'PHP classes', author: 'Danny Adams' },
   //   { title: 'Arrays in PHP', author: 'Danny Adams' },
   // ];
  ```     
  The call-back passed to the filter() function can accept any of the three arguments:
   - the item value
   - the item index
   - the array itself   
- `some()`  
  The some() method checks if some array values pass a test. It returns either *true* or *false*.
  ```js
   let numbers = [4, 6, 14, 16]
   let isSomeGreaterThan6 = numbers.some(n => n > 6) // true
   let isSomeLessThan4 = numbers.some(n => n < 4) // false
  ```     
  The call-back takes 3 arguments:
   - the item value
   - the item index
   - the array itself   
- `every()`  
  every() is similar to the some() method, but checks if every value in the array passes a certain test, rather than just some.
  ```js
   let numbers = [4, 6, 14, 16]
   let isEverythingGreaterThan6 = numbers.every(n => n > 6) // false
   let isEverythingLessThan20 = numbers.some(n => n < 20) // true
  ```     
  The call-back takes 3 arguments:
   - the item value
   - the item index
   - the array itself   
- `flat()`  
  The flat() method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.
  ```js
   let arr = [1, 2, 3, [1, 2], 4]
   let flatArr = arr.flat() // [1, 2, 3, 1, 2, 4]
  ```    
  flat() takes one optional *depth* parameter. *depth* specifies how deep a nested array structure should be flattened. It defaults to 1.  
  ```js
   let arr = [1, 2, 3, [1, 2], [1, [1, 2]]]
   let flatArr1 = arr.flat() // [1, 2, 3, 1, 2, 1, [1, 2]]
   let flatArr2 = arr.flat(2) // [1, 2, 3, 1, 2, 1, 1, 2]
  ```
- `find()`  
  The find() method returns the first element in the array that passes a certain test.
  ```js
   let stock = [
   { item: "ketchup", quantity: 32 },
   { item: "mayo", quantity: 9 },
   { item: "hot sauce", quantity: 12 },
   ]
   let mayo = stock.find(s => s.item === "mayo")
   //  { item: 'mayo', quantity: 9 }
  ```     
  The call-back passed to find() takes 3 arguments:
   - the item value
   - the item index
   - the array itself  
- `findIndex()`  
  Same as find(), but returns the index instead of the value.
  ```js
   let stock = [
   { item: "ketchup", quantity: 32 },
   { item: "mayo", quantity: 9 },
   { item: "hot sauce", quantity: 12 },
   ]
   let mayoIndex = stock.findIndex(s => s.item === "mayo")
   //  1
  ```     
- `sort()`  
  sort() puts an array's elements in ascending order. It is an "in-place" sorting algorithm - meaning that it mutates the original array and returns it.  
  By default, sort() works on strings
  ```js
   let names = ["Zoe", "Adam", "Dan"]
   names.sort()
   console.log(names) // ['Adam', 'Dan', 'Zoe']
  ```  
  For numbers, we need to pass a comparison call-back function
  ```js
   let numbers = [3, 1, 7, 2]
   numbers.sort((a, b) => a - b)
   console.log(numbers) // [1, 2, 3, 7]
  ```
  Initially, a is 3 and b is 1. If a - b is negative, it knows that b is larger, and therefore should come after a. If positive, b should come before a.

&nbsp;

<a name="ch3-1-2"></a>
### 3.1.2 Multi-dimensional Arrays  

You can create an array of arrays, known as a multi-dimensional array, by placing multiple arrays inside a container array. This could be used to create a coordinate system, for example:  

```js
const coordinates = [[1,3],[4,2]];
<< [[1,3],[4,2]]
```

To access the values in a multidimensional array, we use two indices—one to refer to the item’s place in the outer array, and one to refer to its place in the inner array:  

```js
coordinates[0][0]; // The first value of the first array
<< 1
coordinates[1][0]; // The first value of the second array
<< 4
coordinates[0][1]; // The second value of the first array
<< 3
coordinates[1][1]; // The second value of the second array
<< 2
```

&nbsp;

**Creating/Filling NxN Array**  

Here an example for 3-dimensional array:

```js
function _3DimArray (cols, lines) {

    var arr = [];

    for (var i=1; i<=cols; i++){
        arr[i] = [];

        for (var j=1; j<=lines; j++) {
            arr[i][j] = [];
        }
    }
    return arr;
}

// Creating array with size 10x10xN
var container = _3DimArray(10, 10);

// Adding string "item" to cols=2, lines=4
container[2][4].push("item")
```

&nbsp;

# How To's

<a name="ch4-1"></a>
## 4.1 Dynamic variable names  
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

<a name="ch4-2"></a>
## 4.2 Key &rarr; Value / Array  
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
