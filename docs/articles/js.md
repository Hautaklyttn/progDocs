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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1.1 Arrow Function</font>](#ch2-1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1.2 Callbacks</font>](#ch2-1-2)  

### 3. Build-In Types  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1 Arrays</font>](#ch3-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1.1 Common Methods</font>](#ch3-1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.1.2 Multi-dimensional Arrays</font>](#ch3-1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.2 Objects</font>](#ch3-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.3 Classes</font>](#ch3-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">3.4 The Document Object Model (DOM)</font>](#ch3-4)  

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

The most common way to define a function in Javascript is to use a function declaration like the one shown below.  

```js
function hello(){
alert('Hello, World!');
}
```

Another way of defining a function is to create a **function expression**. This assigns an “anonymous function” to a variable  

```js
const goodbye = function(){
alert('Goodbye, World!');
};
```

A function expression is called in the same way as a function declaration—by writing the name of the variable it was assigned to, followed by parentheses:  

```js
goodbye();
```

&nbsp;

Functions always **return** (or output) a value. This can can be specified in the body of the function using the `return` keyword.

**Returning *Undefined***  
If a return value isn’t explicitly stated, it will return `undefined` by default. This is because a function must return a value in order to be considered a function. You’ll often see `undefined` appear in the console after calling a function that in essence is just a procedure and doesn’t need to return a value.  

&nbsp;

**Default Parameters**  
JavaScript provides a convenient way to specify default parameters for a function. These are values that will be used by the function if no arguments are provided when it’s called. To specify a default parameter, you simply assign the default value to it in the function definition. For example, the following function accepts a parameter that’s then added to the end of the string `'Hello '` . The parameter is given a default value of `'World'`:  

```js
function hello(name='World') {
alert(`Hello, ${name}!`);
}
```

Now if we call this function without any arguments, it will default to using `'World'` as the name argument:  

```js
hello();
<< 'Hello, World!'
```

&nbsp;

<a name="ch2-1-1"></a>
### 2.1.1 Arrow Functions  

**Arrow functions** use a less verbose syntax, making them quicker to write, and they’re identified by the “arrow” symbol *( => )* that gives them their name.  

Arrow functions are always anonymous, so if you want to refer to them, you must assign them to a variable, like we did with function  expressions. The example below shows how to create an arrow function that’s assigned to the variable `hola`:  

```js
const hola = () => alert('Hola, Mundo!');
```
The arrow function starts with the parentheses and arrow, *() =>* . Everything after that is the code that will run when the function is called. Notice that this code doesn’t need to be put inside any curly braces (as long as it’s only one line of code), which makes the function appear much more concise.  

Short, one-line functions are good candidates for using arrow functions.

&nbsp;

<a name="ch2-1-2"></a>
### 2.1.2 Callbacks  

A function that’s passed as an argument to another function is known as a **callback**. The callback can then be called from within the body of the function that it’s an argument of. Being able to call different functions from within functions makes functions even more flexible.  

This example is a function that’s called from within the `bake` function and allows us to add some extra information. Update the `bake` function by entering the code below into the console:  

```js
function bake(ingredients,callback){
  console.log(`Mix together ${ingredients}`);
  console.log('Bake in the oven');
  callback();
}
```

Now we can call the bake function with a callback that logs another message to the console. In the example below, the callback is an anonymous arrow function:  

```js
bake('flour, water & sugar', () => console.log('Add icing on top...'));
<< "Mix together flour, water & sugar..."
<< "Bake in the oven...'
<< "Add icing on top..."
```

or

```js
function eat(){
  console.log('Eat every last crumb!');
}

bake('flour,water & sugar', eat);
<< "Mix together flour, water & sugar..."
<< "Bake in the oven...'
<< "Eat every last crumb!"
```

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

<a name="ch3-2"></a>
## 3.2 Objects  

**Objects** are abstract data types used in programming. They can be used to represent real-world objects such as people, animals or places, as well as more abstract concepts such as bank account details, dates or file structures.  

JavaScript is not a class-based language (although you can define classes if you want to). 

> It allows you to create objects quickly and easily without the need for defining a class first.  

Objects can have *properties* and *methods*. **Properties** are information about the object and **methods** are actions that the object can perform. Objects are often used to keep any related information and functionality together in the same place  

Object literals are a distinguishing feature of the JavaScript language, as they allow objects to be created quickly without the need for defining a class, which is common in many other languages. An **object literal** is a self-contained set of related values. Properties can be of almost any data type, such as numbers, strings, Booleans, arrays, or even other objects. If a property is a function, then it’s known as a **method**.  

To create an object literal in JavaScript, simply enter a pair of curly braces.  

```js
const square = {
  sides: 4,
  length: 5,
  perimeter: 20,
  area: 25
}
```

Methods look similar to the other properties, but are defined as a function. The following code shows how we would create an object literal to represent a duck with a quack() method:  

```js
const duck = {
  name: 'Quacky',
  legs: 2,
  quack: function() {
    alert('QUACK! QUACK!');
  }
};
```

You can access the properties and methods of an object using the dot notation.  

```js
elephant.name;
<< "Dumbo"

elephant.fly()
<< "Fly, fly away!"
```

Objects are **mutable** by default, which means that their properties and methods can be changed or removed and new properties and methods can be added, even if they were declared using `const`.  

&nbsp;

It’s even possible for an object to contain other objects. These are known as **nested objects**. 

Here’s an example of an object that contains a group of nested objects. Each nested object represents a different shape. The container object has been assigned to the variable `shapes`:  

```js
const shapes = {
  triangle: { sides: 3 },
  square: { sides: 4 },
  pentagon: { sides: 5 },
  hexagon: { sides: 6 },
  octagon: { sides: 8 },
  megagon: { sides: 10e6 },
}
```

The values in nested objects can be accessed by referencing each property name in order using either dot or bracket notation:  

```js
shapes.triangle.sides;
<< 3
shapes['megagon']['sides'];
<< 1000000
```

&nbsp;

**this**  
The keyword this needs to be be used inside an object to refer to the object itself. It’s often used in methods to gain access to the object’s properties.  

```js
const square = {
  sides: 4,
  length: 5,
  perimeter() { return this.sides * this.length },
  area() { return this.length * this.length }
}
```

&nbsp;

**Constructor function**  

The purpose of a constructor is to **create a new object dynamically** and set values for any existing object properties.

```js
//Constructor function
function User (name, age) {
    this.name = name;
    this.age = age;
}

var user1 = new User('Bob', 25);
var user2 = new User('Alice', 27);
```

To create an object from a constructor function, we use the `new` keyword.

&nbsp;

> An object literal is typically used to create a **single object** whereas a constructor function is useful for creating **multiple objects**.  

> **Note:** It is considered a good practice to capitalize the first letter of your constructor function.

&nbsp;  

<a name="ch3-3"></a>
## 3.3 Classes

... tbd ...

&nbsp;  

<a name="ch3-4"></a>
## 3.4 The Document Object Model (DOM)  

The *Document Object Model*, or *DOM* for short, allows us to **access the elements of a web page** from within our code. It provides tools for adding and removing elements, and for updating the content and style of a page.  

The DOM is **language agnostic**, which means that it can be used in any programming language, although JavaScript is the language it’s most associated with.  

&nbsp;

### The Document Object Model  

> The Document Object Model represents an HTML document as a **network of connected nodes** that form a tree-like structure.  

The DOM treats everything on a web page as a node. It represents HTML tags as **element nodes** and any text inside the tags as **text nodes**. All these nodes are connected to make a node-tree that describes the overall structure of the web page.  

To demonstrate this, let’s take a look at the following short snippet of HTML code:  

```html
<h1 id='greeting'>Hello, <em>World!</em></h1>
```

This can be represented as the node-tree diagram shown below.  

![dt](../assets/pics/domTree.png)  

The `<h1>` tag contains everything, so this appears as an element node at the top of the node tree. The word “Hello” is text, so this is a child text node. The `<em>` element is inside the `<h1>` tag, so it’s a child element node. This makes the `<h1>` element node a parent node of these child nodes. The text inside the `<em>` tags is a text child node of the `<em>` element node.  

> Being able to visualize the HTML markup as a node tree will make navigating the DOM a much easier experience.

&nbsp;

**HTML Document vs the DOM**  
> When you visit a web page, your browser first downloads the page document with all its HTML, text, images and so on. The browser then creates a representation (or mental model, if you like) of that document, which is the *Document Object Model*. Then the browser uses that DOM to display the web page on your device. JavaScript allows changes to be made to the web page, but those changes are made to the DOM, rather than to the original, hard-coded HTML.  

&nbsp;

**Inspecting the DOM**  
> Browsers actually let you view the Document Object Model of a web page, and you can even play around with it in all sorts of ways. (It’s a bit like looking under the hood of a car.) If you right-click anywhere on a web page, you’ll see an option to “inspect” the page. That will display the DOM, along with all sorts of other developer tools. The DOM will look similar to the original HTML, but not exactly the same — especially if JavaScript has modified it.  

&nbsp;

### Getting/Editing an element  

The DOM provides a useful method called `getElementById()` that returns a reference to the element with a particular ID attribute. For example, we can get a reference to the `<h1>` heading element in the previous example using its `id` of `'greeting'`.  

We can get a reference to the `<h1>` element by adding the following code to the JS section:  
```js
const hello = document.getElementById('greeting');
```
We can see what gets returned by typing the name of the variable we assigned the element to ( `hello` ) into the console:  
```html
hello;
<< "<h1 id='greeting'>Hello, <em>World!</em></h1>"
```

As you can see, the variable `hello` now points to the HTML element with the ID of `'greeting'` . Now that we have a reference to that element in our code, it means we can do things with it!  

&nbsp;

The easiest way to update the HTML on a page is to use the `innerHTML` property. This will return all the HTML that’s enclosed inside that element’s tags as a string.  
```html
hello.innerHTML;
<< "Hello, <em>World!</em>"
```

The great thing about the `innerHTML` property is that it’s also writable, so it gives us a convenient way to insert a chunk of HTML inside an element, e.g.  
```js
const name = prompt('What is your name?');
hello.innerHTML = `Hello, <em>${name}!</em>`;
```
Notice that we’ve used a template literal to produce the HTML. These are incredibly useful when creating chunks of HTML to dynamically insert into a web page, as they allow variables to be inserted directly into them.  



&nbsp;

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
