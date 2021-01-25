# Eloquent JavaScript
> By: Alan Nguyen

- [Eloquent JavaScript](#eloquent-javascript)
    - [0. Introduction](#0-introduction)
  - [Part I - Language](#part-i---language)
    - [1. Values, Types, and Operators](#1-values-types-and-operators)
    - [2. Program Structure](#2-program-structure)
    - [3. Functions](#3-functions)
    - [4. Data Structures: Objects and Arrays](#4-data-structures-objects-and-arrays)
    - [5. Higher-Oder Functions](#5-higher-oder-functions)
    - [6. The Secret Life of Objects](#6-the-secret-life-of-objects)
    - [7. Project: A Robot](#7-project-a-robot)
    - [8. Bugs and Errors](#8-bugs-and-errors)
    - [9. Regular Expressions](#9-regular-expressions)
    - [10. Modules](#10-modules)
    - [11 - Asynchronous Programming](#11---asynchronous-programming)
    - [12 - Project: A programming language](#12---project-a-programming-language)
  - [Part II - BROWSER](#part-ii---browser)
    - [13 - JavaScript and the Browser](#13---javascript-and-the-browser)
    - [14 - The Document Object Model](#14---the-document-object-model)
    - [15 - Handling Events](#15---handling-events)
    - [16 - Project: A platform Game](#16---project-a-platform-game)
    - [17 - Drawing on Canvas](#17---drawing-on-canvas)
    - [18 - HTTP and Forms](#18---http-and-forms)
    - [19 - Project: A pixel art editor](#19---project-a-pixel-art-editor)
  - [Part III - NODE](#part-iii---node)
    - [20. Node.js](#20-nodejs)
    - [21. Project: Skill-shareing Website](#21-project-skill-shareing-website)
    - [22. JS and Performance](#22-js-and-performance)


### 0. Introduction

## Part I - Language
### 1. Values, Types, and Operators


### 2. Program Structure

  
### 3. Functions
**#Defining a function**
```javascript
const square = function(x) {
  return x * x;
};
```
**#Bindings & Scope**

**Scope** is the part of the program in which the _binding_ is _visible_.
- **global scope**: bindings defined outside of any _function_ or _block_ 
- **local scope**: declared inside a function or block

**let vs var**
- `let` and `const` create **local bindings** to the block they're declared in
- If `var` is _not in a function_, the bindings will be in the **global scope**

**Nested scope**

Each local scope can also see all the local scopes that contain it, and all scopes can see the global scope.

**#Function as values** ???
- acts as a name for a specific piece of the program

**#Declaration notation**
```javascript
function square(x) {
  return x * x;
}
```
- define the binding `square` and points it at the given function
- doesn't require a semicolon
- this declared function will work even if it's defined _below_ the code that uses it
  - are conceptually moved to the top of their scope

**#Arrow functions**

```js
const funName = (param) => {
  
};
```
- If only one parameter, `()` around parameter can be omitted

```js
const power = (base, exponent) => {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};
```
- If the body is a single expression, don't need to use `return` and `{}`
```js
const square2 = x => x * x;
```
- If an function has no parameters

```js
const horn = () => {
  console.log("Toot");
};
```

**#The call stack**

Def: the call stack is the place where computers stores the context from which the call happened. 
- every time a function is called, the current context is stored on top of this stack

**#Optional arguments**

```js
function square(x) { return x * x; }
console.log(square(4, true, "hedgehog"));
// → 16
```
-  Extra arguments are ignored
- Missing parameters get assigned the value `undefined`
- use `param =` to give a default value

**#Closure**
- Local bindings are created anew for every call
- **Closure** is being able to reference a specific instance of a local binding in an enclosing scope
- A function that references bindings from local scopes around it is called a closure. 
- Allows you to use function values in some creative ways

```js
function multiplier(factor) {
  return number => number * factor;
}

// twice = number => number * 2;
let twice = multiplier(2);
console.log(twice(5));
// → 10
```
> Thinking about programs like this takes some practice

- Think of function values as containing both the **code** in their body and the **environment** in which they are created
- When called, the function body sees the **environment** in which it was **created**, not the environment in which it is called.

**#Recursion**
- Recursive function is the function that calls itself.

```js
function power(base, exponent) {
  if (exponent == 0) {
    return 1;
  } else {
    return base * power(base, exponent - 1);
  }
}

console.log(power(2, 3));
// → 8
```
- 3 times slower than looping version
- Programmer has to balace between human-friendliness and machine-friendliness
- Always start by writing something that’s correct and easy to understand. 
- Most code simply isn’t executed often enough to take any significant amount of time

**#Growing functions**

When you should use function
- Find yourself writing similar code multiple times
- Need some functionality that you haven’t written yet and that sounds like it deserves its own function
- A useful principle is to not add cleverness unless you are absolutely sure you’re going to need it.

**#Functions and side effects**
- A **pure function** is a specific kind of value-producing function that not only has no side effects but also doesn’t rely on side effects from other code

### 4. Data Structures: Objects and Arrays
Numbers, Booleans, and strings are the atoms that data structures are built from

**#Properties**
- Almost all JavaScript values have properties, except `null` and `undefined`.
- properties can be access using
  - `.` notation: `.word` is the literal name of the property
  - `[]` notation: `[expression]` is evaluated to get the property name

**#Methods**
- Methods are properties that contain functions
-  A **stack** is a data structure that allows you to push values into it and pop them out again in the opposite order so that the thing that was added last is removed first. 

**#Objects**
- Properties whose names aren’t valid binding names or valid numbers have to be quoted `"touched tree": "Touched a tree"`
- `in` applies to a string and an object, tells whether that object has a property with that name. Example `"a" in "happy"`
- `Object.keys` returns an array of strings of the object's property names
- `Object.assign` function that copies all properties from one object into another. 
```js
let objectA = {a: 1, b: 2};
Object.assign(objectA, {b: 3, c: 4});
console.log(objectA);
// → {a: 1, b: 3, c: 4}
```
- Arrays are just a kind of object specialized for storing sequences of things.

**#Mutability**
- Numbers, strings, and Booleans, are all immutable
- Objects are mutable
- There is a difference between having two references to the same object and having two different objects that contain the same properties

```js
let object1 = {value: 10};
let object2 = object1;
let object3 = {value: 10};

console.log(object1 == object2);
// → true
console.log(object1 == object3);
// → false

object1.value = 15;
console.log(object2.value);
// → 15
console.log(object3.value);
// → 10
```
`object1` and `object2` have the same _identity_, changing `object1` also changes the value of `object2`.

**#Array Loops**
- Classical JS
```js
for (let i = 0; i < JOURNAL.length; i++) {
  let entry = JOURNAL[i];
  // Do something with entry
}
```
- Modern JS

```js
for (let entry of JOURNAL) {
  console.log(`${entry.events.length} events.`);
}
```
Work for arrays, strings and some other data structures

**#Further Arrayology**
- Methods for adding and removing things at the **start** of an array are called `unshift` and `shift`.

```js
let todoList = [];
function remember(task) {
  todoList.push(task);
}
function getTask() {
  return todoList.shift();
}
function rememberUrgently(task) {
  todoList.unshift(task);
}
```
- To search for a specific value, arrays provide an `indexOf()` method
- To search from the end, there’s a similar method called `lastIndexOf()`

```js
console.log([1, 2, 3, 2, 1].indexOf(2));
// → 1
console.log([1, 2, 3, 2, 1].lastIndexOf(2));
// → 3
```
- Both `indexOf` and `lastIndexOf` take an optional second argument that indicates where to start searching.
- `slice()` takes start and end indices and returns an array that has only the elements between them. The start index is inclusive, the end index exclusive.
- When the end index is not given, slice will take all of the elements after the start index. You can also omit the start index to copy the entire array.
```js
console.log([0, 1, 2, 3, 4].slice(2, 4));
// → [2, 3]
console.log([0, 1, 2, 3, 4].slice(2));
// → [2, 3, 4]
```
-  `concat()` method can be used to glue arrays together to create a new array, similar to what the + operator does for strings

**#Strings and their properties**
- a string’s `indexOf` can search for a string containing more than one character, whereas the corresponding array method looks only for a single element.

```js
console.log("one two three".indexOf("ee"));
// → 11
```
- The `trim` method removes whitespace (spaces, newlines, tabs, and similar characters) from the start and end of a string.

```js
console.log("   okay \n ".trim());
// → okay
```
- split a string on every occurrence of another string with `split` and join it again with `join`

```js
let sentence = "Secretarybirds specialize in stomping";
let words = sentence.split(" ");
console.log(words);
// → ["Secretarybirds", "specialize", "in", "stomping"]
console.log(words.join(". "));
// → Secretarybirds. specialize. in. stomping
```
- A string can be repeated with the `repeat` method, which creates a new string containing multiple copies of the original string, glued together.

```js
console.log("LA".repeat(3));
// → LALALA
```

**#REST parameters**
- accept any number of arguments
- To write such a function, you put three dots before the function’s last parameter

```js
function max(...numbers){ }
```
- You can use a similar three-dot notation to call a function with an array of arguments.

```js
let numbers = [5, 1, 7];
console.log(max(...numbers));
// → 7
```
- Square bracket array notation similarly allows the triple-dot operator to spread another array into the new array.

```js
let words = ["never", "fully"];
console.log(["will", ...words, "understand"]);
// → ["will", "never", "fully", "understand"]
```
**#The Math object**
-  Provides a **namespace** so that its functions and values do not have to be global bindings.

**#Destructuring**

**Array**

`let [n00, n01, n10, n11] = table`

**Object**

`let {name} = {name: "Faraji", age: 23};`

**#JSON**
- Serialize the data - convert into a flat description.
- A popular serialization format is JSON (JavaScript Object Notation)
- Widely used as a data storage and communication format on the web
- **JSON Restrictions**
  - All property names have to be surrounded by `" "`
  - only simple data expressions are allowed
  - no function calls, bindings, or anything that involves actual computation.
  - Comments are not allowed in JSON.
- `JSON.stringigy()` convert JS value to JSON-encoded string
- `JSON.parse()` convert JSON string to JS

```js
let string = JSON.stringify({squirrel: false,
                             events: ["weekend"]});
console.log(string);
// → {"squirrel":false,"events":["weekend"]}
console.log(JSON.parse(string).events);
// → ["weekend"]
```

### 5. Higher-Oder Functions

**#Abstraction**

Abstractions hide details and give us the ability to talk about problems at a higher (or more abstract) level.

**#Higher-order functions**
- are functions that operate on other functions, either by taking them as arguments or by returning them
- allow us to abstract over actions, not just values

- **Functions that creat new functions
**
```js
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
// → true
```
- **Functions that change other functions.**

```js
function noisy(f) {
  return (...args) => {
    console.log("calling with", args);
    let result = f(...args);
    console.log("called with", args, ", returned", result);
    return result;
  };
}
noisy(Math.min)(3, 2, 1);
// → calling with [3, 2, 1]
// → called with [3, 2, 1] , returned 1
```
- **Functions that provide new types of control flow**

```js
function unless(test, then) {
  if (!test) then();
}

repeat(3, n => {
  unless(n % 2 == 1, () => {
    console.log(n, "is even");
  });
});
// → 0 is even
// → 2 is even

```
- `forEach` provides something like a `for/of` loop as a higher-order function.

```js
["A", "B"].forEach(l => console.log(l));
// → A
// → B
```
**#Filtering arrays with `filter`**
- `filter` method filters out the elements in an array that don’t pass a test.

```js
function filter(array, test) {
  let passed = [];
  for (let element of array) {
    if (test(element)) {
      passed.push(element);
    }
  }
  return passed;
}

console.log(filter(SCRIPTS, script => script.living));
// → [{name: "Adlam", ...}, ...]
```
- _pure_ (does not modify the array it's given)

**#Transforming with `map`**
-  `map` method transforms an array by applying a function to all of its elements and building a new array from the returned values.

```js
function map(array, transform) {
  let mapped = [];
  for (let element of array) {
    mapped.push(transform(element));
  }
  return mapped;
}

let rtlScripts = SCRIPTS.filter(s => s.direction == "rtl");
console.log(map(rtlScripts, s => s.name));
// → ["Adlam", "Arabic", "Imperial Aramaic", ...]
```

**#Summarizing with `reduce`**
- It builds a value by repeatedly taking a single element from the array and combining it with the current value

```js
function reduce(array, combine, start) {
  let current = start;
  for (let element of array) {
    current = combine(current, element);
  }
  return current;
}

console.log(reduce([1, 2, 3, 4], (a, b) => a + b, 0));
// → 10
```
- If your array contains at least one element, you are allowed to leave off the start argument

**#Composability**
Higher-order functions start to shine when you need to compose operations.

**#Strings and character codes**
- The `some()` method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.
```js
const array = [1, 2, 3, 4, 5];

// checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// expected output: true
```
- The `findIndex()` method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1, indicating that no element passed the test.
```js
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// expected output: 3

```

### 6. The Secret Life of Objects

Object-oriented programming, a set of techniques that use objects (and related concepts) as the central principle of program organization.

**#Encapsulation**
- Core idea in OOP is to divide programs into smaller pieces and make each piece responsible for managing its own state.
- Different pieces of such a program interact with each other through interfaces,
- public properties that are part of the interface 
- private properties is outside code should not be touching
- Encapsulation is separating interface from implementation is a great idea

**#Method**
- Methods are nothing more than properties that hold function values
- `object.method()` — the binding called `this` in its body automatically points at the object that it was called on.
- Arrow functions are different—they do not bind their own this but can see the this binding of the scope around them.

**#Prototypes**
- A prototype is another object that is used as a fallback source of properties
- Functions derive from Function.prototype, and arrays derive from Array.prototype.

**#Classes**
- A class defines the shape of a type of object—what methods and properties it has. Such an object is called an instance of the class.
- Constructor
  - has to make an object that derives from the proper prototype
  - also has to make sure it, itself, has the properties that instances of this class are supposed to have

```js
function makeRabbit(type) {
  let rabbit = Object.create(protoRabbit);rabbit.type = type;
  return rabbit;}
```
**Class in ES5**
```js
function Rabbit(type) {
   this.type = type;
}
Rabbit.prototype.speak = function(line) {
   console.log(`The ${this.type} rabbit says '${line}'`);
};

let weirdRabbit = new Rabbit("weird");
```
- The names of constructors are capitalized so that they can easily be distinguished from other functions.
- The actual prototype of a constructor is Function.prototype 

**#Class notation**
 - JavaScript classes are constructor functions with a prototype property

**Class in ES6**
```js
class Rabbit {
  constructor(type) {
    this.type = type;
  }
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
}

let killerRabbit = new Rabbit("killer");
let blackRabbit = new Rabbit("black");
```
- Class declarations currently allow only methods—properties that hold functions—to be added to the prototype.
- Like `function`, `class` can be used both in statements and in expressions

**Class used as an expression**

```js
let object = new class { getWord() { return "hello"; } };
console.log(object.getWord());
// → hello
```
- doesn't define a binding
- can omit the class name

**#Overriding derived properties**
- overriding can be used to express exceptional properties in instances of a more generic class of objects

**#Maps**
- A map (noun) is a data structure that associates values (the keys) with other values
```js
let ages    = {
   Boris:   39,
   Liang:   22,
   Julia:   62
};
```
- using plain objects as maps is dangerous
- JS comes with a class `Map` that is written for this exact purpose
  - The methods `set`, `get`, and `has` are part of the interface of the `Map` object.

```js
let ages = new Map();
ages.set("Boris", 39);
ages.set("Liang", 22);
ages.set("Júlia", 62);

console.log(`Júlia is ${ages.get("Júlia")}`);
// → Júlia is 62
console.log("Is Jack's age known?", ages.has("Jack"));
// → Is Jack's age known? false
console.log(ages.has("toString"));
// → false
```
- `Object.keys` returns only an _object’s own keys_, not those in the `prototype`
- As an alternative to the `in` operator, you can use the `hasOwnProperty` method, which ignores the object’s prototype
```js
console.log({x: 1}.hasOwnProperty("x"));
// → true
console.log({x: 1}.hasOwnProperty("toString"));
// → false
```

**#Polymorphism**
- Def. when a piece of code is written to work with objects that have a certain interface, any kind of object that happens to support this interface can be plugged into the code, and it will just work 

**#Symbols**
- Unlike strings, newly created symbols are unique—you cannot create the same symbol twice.
- The string you pass to `Symbol` is included when you convert it to a string 
- Being both unique and usable as property names makes symbols suitable for defining interfaces 
- It is possible to include symbol properties in object expressions and classes by using square brackets around the property name. 
```js
let stringObject = {
   [toStringSymbol]() { return "a jute rope"; }
};
console.log(stringObject[toStringSymbol]());
// → a jute rope
```
**#The iterator interface**



**#Getters, setters, and statics**


**#Inheritance**

**#The `instanceOf` opertor**


### 7. Project: A Robot

### 8. Bugs and Errors

**#Exceptions**
- Exception handling - when a function cannot proceed normally, what we would like to do is just stop what we are doing and immediately jump to a place that knows how to handle the problem
- unwinding the stack - raising one somewhat resembles a super-charged return from a function: it jumps out of not just the current function but also its callers, all the way down to the first call that started the current execution.
- `throw` keyword is used to raise an exception. 

```js
throw new Error("Invalid direction: " + result);
```

- When the code in the `try` block causes an exception to be raised, the `catch` block is evaluated, with the name in parentheses bound to the exception value. 
- 

```js
try {
  console.log("You see", look());
} catch (error) {
  console.log("Something went wrong: " + error);
}
```
- Big advantage of exceptions: error-handling code is necessary only at the point where the error occurs and at the point where it is handled.
- 
### 9. Regular Expressions

### 10. Modules

### 11 - Asynchronous Programming 


### 12 - Project: A programming language

## Part II - BROWSER

### 13 - JavaScript and the Browser
A network protocol describes a style of communication over a network. 

### 14 - The Document Object Model

### 15 - Handling Events

### 16 - Project: A platform Game

### 17 - Drawing on Canvas

### 18 - HTTP and Forms

**The Protocol**
- Look up the address of the server associated the website
- Open a TCP connection (port 80 - default port for HTTP traffic)

**Status codes**
- 2 - succeeded
- 4 - request error
- 5 - server error

GET and DELETE requests: no data sent
PUT and POST requests: data sent

### 19 - Project: A pixel art editor


## Part III - NODE

### 20. Node.js
asynchronous programming - allows the program to send and receive data from and to multiple devices at the same time without complicated thread management and synchronization. 

/ - the root of the file system
./ - current directory
../ - one directory up 

NMP - an online repository of JS modules 
npm init             -> create package.json
npm install        -> install the dependencies listed in pakage.json
### 21. Project: Skill-shareing Website

### 22. JS and Performance
