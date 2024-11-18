# JavaScript Documentation by Brave

JavaScript is a **multi-paradigm programming language**, meaning it supports multiple styles of programming, including **functional programming**, **object-oriented programming (OOP)**, and **procedural programming**. JavaScript is used for dynamic websites, web extensions, handling events, validating forms, manipulating the DOM, animations, asynchronous operations (API calls), building real-time apps, games, backend services (Node.js), and data visualization (e.g., Chart.js).

# Method, Property, Parameters, Arguments:

- **Method:** A function associated with an object in the context of OOP.
- **Property:** A characteristic or attribute of an object representing its state.
- **Parameters:** Variables used in a function or method definition.
- **Arguments:** Values passed to a function or method when it is called.

**Method:**

```jsx
class Dog {
  bark() {
    console.log("Woof! Woof!");
  }
}

const myDog = new Dog();
myDog.bark(); // Calling the bark method of the Dog class
```

**Property**

```jsx
class Car {
  constructor(make, model) {
    this.make = make; // Property: make
    this.model = model; // Property: model
  }
}

const myCar = new Car("Toyota", "Camry");
console.log(myCar.make); // Accessing the make property of the Car object
```

**Parameters:**

```jsx
function add(a, b) {
  return a + b;
}

const result = add(3, 5); // 3 and 5 are arguments passed to the add function
console.log(result); // Output: 8
```

**Argument:**

```jsx
function greet(name) {
  console.log(`Hello, ${name}!`);
}

greet("Alice"); // "Alice" is the argument passed to the greet function
```

> (counting) Array & String index start from Zero! It’s element start from One!
> 

> In JavaScript array & object is by default mutable (not Immutable)
- meaning you can modify their content even if they are declared with `const`
- To prevent that use `object.freeze()`. `const obj = Object.freeze({ name: "Brave" });`.
> 

# Operators in JavaScript:

**1. Arithmetic Operators:**
Arithmetic operators perform basic mathematical calculations.

```jsx
let x = 10;
let y = 5;

let addition = x + y;      // 15
let subtraction = x - y;   // 5
let multiplication = x * y; // 50
let division = x / y;       // 2
let remainder = x % y;      // 0 (remainder of division)

let increment = x++; // increment x by 1
let decrement = y--; // decrement y by 1
```

**2. Assignment Operators:**
Assignment operators are used to assign values to variables.

```jsx
let a = 10;

a = b; // b now holds the value of a (10)
a += 5; // equivalent to a = a + 5; (15)
a -= 3; // equivalent to a = a - 3; (12) (15 - 3)
a *= 2; // equivalent to a = a * 2; (24) (12 * 2)
a /= 4; // equivalent to a = a / 4; (6) (24 / 4)
a %= 2; // equivalent to a = a % 2; (0) (6 % 2)
```

**3. Comparison Operators:**
Comparison operators compare values and return a Boolean result (true or false).

```jsx
let p = 10;
let q = 5;

let isEqual = p === q; // false (strict equality)
let isNotEqual = p !== q; // true (strict inequality)
let isGreater = p > q; // true
let isLess = p < q; // false
let isGreaterOrEqual = p >= q; // true (First condition is true (greater), the result is true.)
let isLessOrEqual = p <= q; // false
```

**Short Note:**

- **JavaScript:**
    - `=`: Assignment.
    - `==`: Value equality with type coercion.
    - `===`: Strict equality (value & type).
- **Python:**
    - `=`: Assignment.
    - `==`: Value equality (no type coercion).

**Coercion** means **automatically converting one data type to another** during operations.

Coercion example:

```jsx
let x = 5;
let y = "10";
console.log(x + y); // Output: "510"
```

This example shows JavaScript coercing the number 5 to a string when added to "10".

**4. Logical Operators:**
Logical operators are used to combine or manipulate Boolean values.

```jsx
let sunny = true;
let warm = true;

let isNiceWeather = sunny && warm; // true (logical AND)
let isEitherOr = sunny || warm; // true (logical OR)
let isNotSunny = !sunny; // false (logical NOT)
```

**5. Ternary Operator (Conditional Operator):**
The conditional (ternary) operator **`? :`** is a concise way to write simple conditional statements.

```jsx
let age = 18;
let canVote = age >= 18 ? "Yes" : "No"; // "Yes"
```

**6. Bitwise Operators (Advanced):**
Bitwise operators manipulate the binary representation of numbers.

```jsx
let x = 5;  // Binary: 0101
let y = 3;  // Binary: 0011

let bitwiseAnd = x & y;  // 1 (Binary: 0001)
let bitwiseOr = x | y;   // 7 (Binary: 0111)
let bitwiseXor = x ^ y;  // 6 (Binary: 0110)
let bitwiseNotX = ~x;    // -6 (Binary: 1010)
let leftShift = x << 1;  // 10 (Binary: 1010)
let rightShift = x >> 1; // 2 (Binary: 0010)
```

**8. Spread Operator (Advanced):**

The spread operator (`...`) expands elements of arrays or objects into individual items or properties.

```jsx
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 }; // { a: 1, b: 2, c: 3 }
```

# Variables:

Variables are used to store data that you want to use and manipulate in your programs. They give your code the ability to remember values and use them later. In JavaScript, you can declare variables using different keywords: `var`, `let`, and `const`.

**1. `var`:**`var` was historically the primary keyword used to declare variables in JavaScript, but it has some issues related to scope.

- Variables declared with `var` have function scope or global scope.
- They are hoisted, meaning they are moved to the top of their scope during the compilation phase.

```jsx
function example() {
  var x = 5;
  if (true) {
    var x = 10;  // This actually modifies the 'x' declared above
    console.log(x);  // Output: 10
  }
  console.log(x);  // Output: 10
}

example();
```

As you can see, the value of `x` is modified both inside and outside the `if` block.

**2. `let`:**`let` was introduced in ES6 (ECMAScript 2015) to address some of the issues of `var`. It has block scope.

- Variables declared with `let` have block scope, which means they are limited to the block in which they're declared.
- They are not hoisted to the entire scope, only to the block they are declared in.

```jsx
function example() {
  let x = 5;
  if (true) {
    let x = 10;  // This creates a separate 'x' within the block
    console.log(x);  // Output: 10
  }
  console.log(x);  // Output: 5
}

example();
```

Here, the `x` inside the `if` block is a different variable from the `x` declared outside the block.

**3. `const`:**`const` is used to declare constants - variables whose values shouldn't change after assignment.

- Variables declared with `const` have block scope.
- Once assigned a value, a `const` variable cannot be reassigned.

```jsx
const pi = 3.14159;
// pi = 3.14;  // This would result in an error, as you can't reassign a constant variable.
```

```jsx
const person = { name: "Alice" };
person.age = 30;  // You can modify properties of a constant object.
console.log(person);  // Output: { name: "Alice", age: 30 }
```

In the second example, while you can't reassign the `person` variable itself, you can still modify its properties.

**Choosing Between `let` and `const`:**

- Use `let` when you expect the value of the variable to change over time.
- Use `const` when you want to declare a variable with a constant, unchanging value.

In general, it's a good practice to use `const` by default and only use `let` when you're sure the value will change.

# Data Types:

JavaScript has **8 data types**, categorized as **primitive** and **non-primitive (complex):**

1. **Number**
2. **BigInt**
3. **String**
4. **Boolean**
5. **Undefined**
6. **Null**
7. **Symbol**
8. **Object**

---

**1. Primitive Data Types:**
Primitive data types are simple, immutable values. They are directly assigned and copied by value.

**a. Number:**
Used for numeric values.

```jsx
let age = 25;
let temperature = 98.6;
```

**b. String:**
Used for text values. Enclosed in single ('') or double ("") quotes.

```jsx
let name = "Alice";
let message = 'Hello, ' + name;
```

**c. Boolean:**
Used for true or false values.

```jsx
let isStudent = true;
let isWorker = false;
```

**d. Undefined:**
Represents a variable that's been declared but not assigned a value.

```jsx
let x;
console.log(x); // Output: undefined
```

**e. Null:**
Represents an intentional absence of any value or object.

```jsx
let emptyValue = null;
```

**f. Symbol (ES6):**
Represents a unique and immutable value, often used for object property keys.

```jsx
let uniqueKey = Symbol("description");
```

**2. Object Data Type:**
Objects are collections of key-value pairs, where values can be of any data type.

```jsx
let person = {
  name: "John",
  age: 30,
  isStudent: false
};
```

**3. Array Data Type:**
Arrays are ordered lists of values, accessed by index.

```jsx
let colors = ["red", "green", "blue"];
console.log(colors[0]); // Output: "red"
```

**4. Function Data Type:**
Functions are blocks of reusable code that perform specific tasks.

```jsx
function greet(name) {
  console.log("Hello, " + name + "!");
}
```

**5. Advanced Data Types:**
JavaScript has advanced data types that are built on top of primitive data types.

**a. Date:**
Used to work with dates and times.

```jsx
let currentDate = new Date();
console.log(currentDate);
```

**b. RegExp (Regular Expression):**
Used for pattern matching within strings.

```jsx
let pattern = /[0-9]+/;
let result = pattern.test("123"); // true
```

**c. Map and Set (ES6):**
Map stores key-value pairs, and Set stores unique values.

```jsx
let myMap = new Map();
myMap.set("name", "Alice");

let mySet = new Set();
mySet.add(10);
mySet.add(20);
```

**Remember:**

- JavaScript has primitive and advanced data types.
- Primitive data types are simple values.
- Objects and arrays are complex data types.
- Functions are reusable blocks of code.
- Advanced data types include Date, RegExp, Map, and Set.

# Regular expressions:

Regular expressions, often referred to as RegEx, are powerful patterns used for **string matching** and manipulation. They allow you to **search, replace, and validate strings based on specific patterns**. (Usually we don’t remember it when we need it, we just search on Internet)

**1. Creating a Regular Expression:**
Regular expressions are created using literal notation or the `RegExp` constructor.

```jsx
// Literal notation (using slashes)
let pattern = /abc/;

// Using RegExp constructor
let pattern = new RegExp("abc");
```

**2. Basic Matching:**
You can use regular expressions to match strings against a pattern.

```jsx
let text = "Hello, world!";
let pattern = /world/;
let result = pattern.test(text); // true
```

**3. Special Characters:**
Regular expressions use special characters to define patterns.

- `.`: Matches any character except a newline.
- ``: Matches zero or more occurrences of the preceding character.
- `+`: Matches one or more occurrences of the preceding character.
- `?`: Matches zero or one occurrence of the preceding character.
- `[]`: Defines a character set.
- `^`: Matches the beginning of a string.
- `$`: Matches the end of a string.

```jsx
let text = "Hello, world!";
let pattern = /w..ld/;
let result = pattern.test(text); // true
```

**4. Character Sets:**
You can use square brackets to define a set of characters to match.

```jsx
let pattern = /[aeiou]/; // Matches any vowel
```

**5. Quantifiers:**
Quantifiers specify how many times a character or group should appear.

- `{n}`: Matches exactly `n` occurrences.
- `{n,}`: Matches `n` or more occurrences.
- `{n,m}`: Matches between `n` and `m` occurrences.

```jsx
let pattern = /\\d{3}-\\d{2}-\\d{4}/; // Matches a social security number like "123-45-6789"
```

**6. Flags:**
Flags modify the behavior of regular expressions.

- `i`: Case-insensitive matching.
- `g`: Global matching (find all occurrences).
- `m`: Multi-line matching.

```jsx
let text = "Hello, Hello, World!";
let pattern = /hello/gi;
let result = text.match(pattern); // ["Hello", "Hello"]
```

**7. Groups and Capturing:**
Parentheses `()` define groups and capture matched portions.

```jsx
let text = "apple, banana, cherry";
let pattern = /(apple|banana)/g;
let result = text.match(pattern); // ["apple", "banana"]
```

**8. Metacharacters:**
Some characters have special meanings and need to be escaped with a backslash `\\`.

```jsx
let text = "Price: $25.99";
let pattern = /\\$/g; // Match the dollar sign
```

# Js Functions:

Functions are one of the fundamental building blocks in JavaScript. They allow you to group and encapsulate code that performs a specific task. (It just care about the code inside it and run that)

**1. Defining a Function:**
Functions are defined using the `function` keyword, followed by the function name, parameters in parentheses, and the function body in curly braces.

```jsx
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet("Alice"); // Output: "Hello, Alice!"
```

**2. Function Parameters and Arguments:**
Parameters are placeholders for values that a function will receive when called. Arguments are the actual values passed to the function when it's called.

```jsx
function add(a, b) { // a, b are the PARAMETERS
  return a + b;     
}

let result = add(5, 3); // 5 and 3 are the ARGUMENTS passed to the function
console.log(result);    // Output: 8
```

**3. Return Statement:**
The `return` statement specifies the value that a function will return when called. If no `return` statement is used, the function returns `undefined`.

```jsx
function multiply(a, b) {
  return a * b;
}

let product = multiply(4, 7); // 28
```

`return` also stop the execution (skip it)

```jsx
function test(num) {
  if (num > 10) return "Greater";  // Stops execution if true
  return "Less or equal";
}

console.log(test(15)); // Output: "Greater"
console.log(test(5));  // Output: "Less or equal"
```

**4. Function Expressions:**
Functions can also be assigned to variables as function expressions.

```jsx
let sayHello = function(name) {
  console.log("Hello, " + name + "!");
};

sayHello("Bob"); // Output: "Hello, Bob!"
```

**5. Arrow Functions (ES6):**
Arrow functions provide a more concise syntax for defining functions, especially for short functions with single expressions.

```jsx
let square = (x) => x * x;

let result = square(5); // 25
```

**6. Higher-Order Functions:**
Functions that take other functions as arguments or return functions are called higher-order functions. They enable powerful functional programming techniques.

```jsx
function applyOperation(x, operation) {
  return operation(x);
}

let squareResult = applyOperation(4, (num) => num * num); // 16
```

**7. Closures:**
A closure occurs when an inner function retains access to the variables of its outer function, even after the outer function has finished executing.

```jsx
function outer() {
  let outerVar = "I'm from outer function";

  function inner() {
    console.log(outerVar);  // Outer variable accessible here due to closure
  }

  return inner;
}

let closureFunc = outer();
closureFunc();  // Outputs: "I'm from outer function"
```

**8. Callback Functions:**
A callback function is a function that is passed as an argument to another function and is executed later.

```jsx
function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

greet("Brave", () => console.log("Goodbye!"));
// Output:
// Hello, Brave
// Goodbye!
```

The callback function is defined directly inside the `greet` function call.

# Js Objects:

Objects are a cornerstone of JavaScript and play a crucial role in representing complex data structures.

**1. Creating Objects:**
Objects in JavaScript are created using curly braces `{}`. They can hold properties (key-value pairs) and methods (functions associated with the object).

```jsx
let person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  sayHello: function() {
    console.log("Hello!");
  }
};
```

**2. Accessing Object Properties:**
Object properties can be accessed using dot notation (`objectName.propertyName`) or bracket notation (`objectName['propertyName']`).

```jsx
console.log(person.firstName); // Output: "John"
console.log(person['age']); // Output: 30
```

**3. Adding and Modifying Properties:**
You can add new properties or modify existing ones using assignment.

```jsx
person.job = "Developer"; // Adding a new property
person.age = 31; // Modifying an existing property
```

**4. Deleting Properties:**
The `delete` operator can be used to remove a property from an object.

```jsx
delete person.job; // Removing the "job" property
```

**5. Object Methods:**
Methods are functions that are stored as object properties. They can perform actions related to the object.

```jsx
person.sayHello(); // Calling the method
```

**6. Object Constructors:**
You can use constructor functions to create multiple objects with similar properties and methods.

```jsx
function Car(make, model) {
  this.make = make;
  this.model = model;
  this.drive = function() {
    console.log("Vroom vroom!");
  };
}

let myCar = new Car("Toyota", "Corolla");
myCar.drive(); // Output: "Vroom vroom!"
```

**7. Object Prototypes (Advanced):**
In JavaScript, each object is associated with a prototype object that allows you to share properties and methods among objects.

```jsx
Car.prototype.honk = function() {
  console.log("Honk honk!");
};

myCar.honk(); // Output: "Honk honk!"
```

**8. Object Destructuring (ES6):**
Destructuring allows you to extract properties from objects and assign them to variables.

```jsx
let { firstName, lastName } = person;
console.log(firstName); // Output: "John"
```

**9. Object Spread (ES6):**
Spread syntax allows you to create new objects by copying properties from an existing object.

```jsx
let newPerson = { ...person, age: 32 }; // ... - (...person) is Spread Operator
```

**10. Object Composition:**
You can compose complex objects by combining smaller objects together.

```jsx
let address = {
  street: "123 Main St",
  city: "Anytown"
};

let completePerson = { ...person, ...address };
```

**11. Object Methods and `this`:**
When a method is called, the `this` keyword refers to the object that the method belongs to.

```jsx
let person = {
  firstName: "John",
  sayHello: function() {
    console.log("Hello, " + this.firstName + "!");
  }
};
person.sayHello(); // Output: "Hello, John!"
```

**12. Object Privacy (Closures):**
Closures can be used to create private variables and methods within objects.

```jsx
function createCounter() {
  let count = 0;
  return {
    increment: function() {
      count++;
    },
    getCount: function() {
      return count;
    }
  };
}

let counter = createCounter();
counter.increment();
console.log(counter.getCount()); // Output: 1
```

# Js Array:

Arrays are a fundamental data structure in JavaScript used to store and manage collections of values. They provide a way to organize related data and perform various operations on that data.

**1. Creating Arrays:**
Arrays are created using square brackets `[]`, and they can hold any type of values, including numbers, strings, objects, and even other arrays.

```jsx
let numbers = [1, 2, 3, 4, 5];
let fruits = ["apple", "banana", "cherry"];
```

**2. Accessing Array Elements:**
Array elements are accessed using their index, which starts from `0`.

```jsx
console.log(numbers[0]); // Output: 1
console.log(fruits[2]); // Output: "cherry"
```

**3. Modifying Array Elements:**
You can modify array elements by assigning new values to specific indices.

```jsx
numbers[1] = 10; // Modifying the second element to 10
fruits[0] = "orange"; // Modifying the first element to "orange"
```

**4. Array Methods:**

- **Elements**: In the context of an array, elements refer to the individual items contained within the array. For example, in the array **`numbers = [1, 2, 3, 4, 5]`**, each number (1, 2, 3, 4, 5) is an element of the array.
- **Index**: An index is a numerical representation of the position of an element within an array. In JavaScript, array indexes start at 0. So, in the array **`numbers = [1, 2, 3, 4, 5]`**, the index of the element **`1`** is **`0`**, the index of the element **`2`** is **`1`**, and so on.

```jsx
// Original array
const numbers = [1, 2, 3, 4, 5];

// 1. map(): creates a transformed version based on the callback you provide. 
const doubledNumbers = numbers.map(num => num * 2);
// For this code Explanation: Creates a new array with the doubled values of each element in the original array.
// Answer: doubledNumbers = [2, 4, 6, 8, 10]

// 2. filter(): Filters out even numbers from the array
const oddNumbers = numbers.filter(num => num % 2 !== 0);
// Explanation: Creates a new array with only the odd numbers from the original array.
// Answer: oddNumbers = [1, 3, 5]

// 3. reduce(): Calculates the sum of all numbers in the array
const sum = numbers.reduce((acc, num) => acc + num, 0);
// Explanation: Applies a function against an accumulator and each element in the array to reduce it to a single value, which is the sum of all numbers.
// Answer: sum = 15

// 4. forEach(): Prints each number in the array
const count = numbers.forEach(num => console.log(num));
// Explanation: Executes a provided function once for each array element.
// Output: 1
//         2
//         3
//         4
//         5

// 5. find(): Finds the first even number in the array
const firstEvenNumber = numbers.find(num => num % 2 === 0);
// Explanation: Returns the first element in the array that satisfies the provided testing function.
// Answer: firstEvenNumber = 2

// 6. findIndex(): Finds the index of the first even number in the array
const indexOfFirstEven = numbers.findIndex(num => num % 2 === 0);
// Explanation: Returns the index of the first element in the array that satisfies the provided testing function.
// Answer: indexOfFirstEven = 1

// 7. some(): Checks if any number in the array is greater than 5
const hasGreaterThanFive = numbers.some(num => num > 5);
// Explanation: Checks if at least one element in the array satisfies the provided testing function.
// Answer: hasGreaterThanFive = true

// 8. every(): Checks if all numbers in the array are less than 10
const allLessThanTen = numbers.every(num => num < 10);
// Explanation: Checks if all elements in the array satisfy the provided testing function.
// Answer: allLessThanTen = true

// 9. sort(): Sorts the numbers in ascending order
const sortedNumbers = numbers.sort((a, b) => a - b);
// Explanation: Sorts the elements of the array in place and returns the sorted array.
// Answer: sortedNumbers = [1, 2, 3, 4, 5]

// 10. slice(): Copies a portion of the array (from index 1 to index 3)
const slicedNumbers = numbers.slice(1, 4);
// Explanation: Returns a shallow copy of a portion of the array into a new array object selected from start to end.
// Answer: slicedNumbers = [2, 3, 4]

// 11. concat(): Concatenates two arrays
const moreNumbers = [6, 7, 8];
const concatenatedNumbers = numbers.concat(moreNumbers);
// Explanation: Returns a new array comprised of the array on which it is called joined with the array(s) provided as arguments.
// Answer: concatenatedNumbers = [1, 2, 3, 4, 5, 6, 7, 8]

// 12. indexOf(): Finds the index of number 3 in the array
const indexOfThree = numbers.indexOf(3);
// Explanation: Returns the first index at which a given element can be found in the array, or -1 if it is not present.
// Answer: indexOfThree = 2

// 13. lastIndexOf(): Finds the last index of number 3 in the array
const lastIndexOfThree = numbers.lastIndexOf(3);
// Explanation: Returns the last index at which a given element can be found in the array, or -1 if it is not present.
// Answer: lastIndexOfThree = 2

// 14. includes(): Checks if the array includes number 5
const includesFive = numbers.includes(5);
// Explanation: Determines whether an array includes a certain value among its entries, returning true or false as appropriate.
// Answer: includesFive = true

// 15. splice(): Removes elements from an array and/or inserts new elements
const removedElements = numbers.splice(1, 2);
// Explanation: Removes elements from the original array starting at index 1 and removes 2 elements. Returns the removed elements.
// After this operation, numbers = [1, 4, 5], removedElements = [2, 3]

// 16. shift(): Removes the first element from an array
const shiftedElement = numbers.shift();
// Explanation: Removes the first element from the original array and returns that element.
// After this operation, numbers = [4, 5], shiftedElement = 1

// 17. unshift(): Adds elements to the beginning of an array
numbers.unshift(0);
// Explanation: Adds one or more elements to the beginning of the original array and returns the new length of the array.
// After this operation, numbers = [0, 4, 5]

// 18. pop(): Removes the last element from an array
const lastElement = numbers.pop();
// Explanation: Removes the last element from the original array and returns that element.
// After this operation, numbers = [0, 4], lastElement = 5

// 19. push(): Adds elements to the end of an array
numbers.push(6);
// Explanation: Adds one or more elements to the end of the original array and returns the new length of the array.
// After this operation, numbers = [0, 4, 6]
```

### Common Methods in **JavaScript Arrays** and **Python Lists**:

1. **`push()` / `append()`**
    - Adds element at the end
    - **JS:** `arr.push(value)`
    - **Python:** `lst.append(value)`
2. **`pop()`**
    - Removes and returns the last element
    - **JS:** `arr.pop()`
    - **Python:** `lst.pop()`
3. **`shift()` / `remove(0)`**
    - Removes the first element
    - **JS:** `arr.shift()`
    - **Python:** `lst.pop(0)`
4. **`unshift()` / `insert(0, value)`**
    - Adds element at the beginning
    - **JS:** `arr.unshift(value)`
    - **Python:** `lst.insert(0, value)`
5. **`length()` / `len()`**
    - Length of array
    - **JS:** `arr.length`
    - **Python:** `len(lst)`
6. **`slice()`**
    - Copies a portion of the array
    - **JS:** `arr.slice(start, end)`
    - **Python:** `lst[start:end]`
7. **`forEach()` / `for` loop**
    - Iterates through elements
    - **JS:** `arr.forEach(callback)`
    - **Python:** `for item in lst:`
8. **`map()`**
    - **JS:** `arr.map(callback)`
        - Transforms each element into a new array
    - **Python:** `map(func, lst)`
        - Applies a function to each element
9. **`filter()`**
    - Filters elements based on condition
    - **JS:** `arr.filter(callback)`
    - **Python:** `filter(func, lst)`
10. **`sort()`**
- Sorts array in place
- **JS:** `arr.sort()`
- **Python:** `lst.sort()`

**5. Iterating Over Arrays:**
loop through array elements using various methods.

- `for` loop: Traditional loop for iterating through indices.
- `for...of` loop: Modern loop for iterating through values.
- `forEach()`: Calls a function for each element.

```jsx
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

for (let fruit of fruits) {
  console.log(fruit);
}

fruits.forEach(function(fruit) {
  console.log(fruit);
});
```

# **JavaScript Set**

A `Set` is a collection of unique values. Unlike arrays, a `Set` only stores distinct elements and does not allow duplicates.

**Common Methods:**

1. **`add(value)`**: Adds a value to the set (if it's not already present).
    
    ```jsx
    let mySet = new Set();
    mySet.add(1);
    mySet.add(2);
    ```
    
2. **`delete(value)`**: Removes a value from the set.
    
    ```jsx
    mySet.delete(1);
    ```
    
3. **`has(value)`**: Checks if a value is present in the set.
    
    ```jsx
    mySet.has(2); // true
    ```
    
4. **`clear()`**: Removes all values from the set.
    
    ```jsx
    mySet.clear();
    ```
    
5. **`size`**: Returns the number of elements in the set.
    
    ```jsx
    mySet.size;
    ```
    

**Why Use a `Set` vs an Array?**

- **Uniqueness**: A `Set` automatically ensures that all elements are unique, whereas an array can have duplicate values.
- **Performance**: Operations like checking for the existence of an element (`has()`) are faster in a `Set` compared to an array (`indexOf()` or `includes()`), especially with large datasets.
- **Order**: Both arrays and sets maintain insertion order, but arrays allow duplicates and have more flexible methods for accessing and manipulating data.

# Js Strings:

**1. Creating Strings:**
Strings are sequences of characters. You can create them using single or double quotes.

```jsx
let greeting = "Hello, world!";
let name = 'Alice';
```

**2. Escaping Characters:**
You can use the backslash `\\` to escape special characters within strings.

```jsx
let message = "She said, \\"Hello!\\"";
let path = "C:\\\\Users\\\\Username\\\\Documents";
```

**3. String Length:**
The `length` property returns the number of characters in a string.

```jsx
let sentence = "This is a long sentence."; //counting start with 0 
console.log(sentence.length); // Output: 24
```

**4. String Methods:**
Strings have built-in methods for various operations:

```jsx
// Original string
const str = "Hello, World!";

// Count the number of characters in the string
const characterCount = str.length;
// Explanation: Returns the number of characters in the string.
// Answer: characterCount = 13

// 1. toUpperCase(): Converts the string to uppercase
const upperCaseStr = str.toUpperCase();
// Explanation: Converts all characters in the string to uppercase.
// Answer: upperCaseStr = "HELLO, WORLD!"

// 2. toLowerCase(): Converts the string to lowercase
const lowerCaseStr = str.toLowerCase();
// Explanation: Converts all characters in the string to lowercase.
// Answer: lowerCaseStr = "hello, world!"

// 3. charAt(): Returns the character at a specified index (index 7)
const charAtIndex7 = str.charAt(7);
// Explanation: Returns the character at the specified index in the string.
// Answer: charAtIndex7 = "W"

// 4. indexOf(): Returns the index of the first occurrence of a specified substring ("World")
const indexOfWorld = str.indexOf("World");
// Explanation: Returns the index of the first occurrence of the specified substring in the string.
// Answer: indexOfWorld = 7

// 5. slice(): Extracts a section of the string (from index 7 to index 12)
const slicedStr = str.slice(7, 12);
// Explanation: Returns a substring of the string starting from the specified start index to the specified end index (excluding the end index).
// Answer: slicedStr = "World"

// 6. replace(): Replaces a specified substring with another substring ("World" with "Universe")
const replacedStr = str.replace("World", "Universe");
// Explanation: Returns a new string with all occurrences of a specified substring replaced by another substring.
// Answer: replacedStr = "Hello, Universe!"

// 7. split(): Splits the string into an array of substrings based on a specified delimiter (", ")
const splitStr = str.split(", ");
// Explanation: Splits the string into an array of substrings based on the specified delimiter.
// Answer: splitStr = ["Hello", "World!"]

// 8. trim(): Removes whitespace from both ends of the string
const trimmedStr = "   Hello, World!   ".trim();
// Explanation: Removes whitespace from both ends of the string.
// Answer: trimmedStr = "Hello, World!"
// trimStart() and trimEnd() Also exist!

// 9. startsWith(): Checks if the string starts with a specified substring ("Hello")
const startsWithHello = str.startsWith("Hello");
// Explanation: Checks if the string starts with the specified substring.
// Answer: startsWithHello = true

// 10. endsWith(): Checks if the string ends with a specified substring ("World!")
const endsWithWorld = str.endsWith("World!");
// Explanation: Checks if the string ends with the specified substring.
// Answer: endsWithWorld = true

// 11. endsWith(): Check if the string contains a specified substring ("World")
const includesWorld = str.includes("World");
// Explanation: Checks if the string contains the specified substring.
// Answer: includesWorld = true

// 12. match(): Searches a string for a match against a regular expression
const matches = str.match(/World/g);
// Explanation: Searches the string for matches against the regular expression /World/g and returns an array of all matches found.
// Answer: matches = ["World"]
```

### Common Methods in **JavaScript Strings** and **Python Strings**:

1. **`length()` / `len()`**
    - Length of string
    - **JS:** `str.length`
    - **Python:** `len(str)`
2. **`toUpperCase()` / `upper()`**
    - Converts string to uppercase
    - **JS:** `str.toUpperCase()`
    - **Python:** `str.upper()`
3. **`toLowerCase()` / `lower()`**
    - Converts string to lowercase
    - **JS:** `str.toLowerCase()`
    - **Python:** `str.lower()`
4. **`trim()` / `strip()`**
    - Removes whitespace from both ends
    - **JS:** `str.trim()`
    - **Python:** `str.strip()`
5. **`indexOf()` / `find()`**
    - Finds the index of a substring
    - **JS:** `str.indexOf(substring)`
    - **Python:** `str.find(substring)`
6. **`substring()` / `slice()`**
    - Extracts a part of the string
    - **JS:** `str.substring(start, end)`
    - **Python:** `str[start:end]`
7. **`replace()` / `replace()`**
    - Replaces a substring with another string
    - **JS:** `str.replace(old, new)`
    - **Python:** `str.replace(old, new)`
8. **`split()`**
    - Splits the string into an array/list
    - **JS:** `str.split(separator)`
    - **Python:** `str.split(separator)`
9. **`charAt()` / `__getitem__()`**
    - Returns the character at a specific index
    - **JS:** `str.charAt(index)`
    - **Python:** `str[index]`
10. **`includes()` / `in`**
- Checks if a substring exists in the string
- **JS:** `str.includes(substring)`
- **Python:** `substring in str`

**5. String Concatenation:**
You can combine strings using the `+` operator or template literals (backticks).

```jsx
let firstName = "John";
let lastName = "Doe";

let fullName = firstName + " " + lastName;
let greeting = `Hello, ${fullName}!`;
```

**6. Unicode and UTF-16:**
JavaScript uses UTF-16 encoding to represent characters, allowing you to work with various languages and special characters.

```jsx
let smiley = "\\uD83D\\uDE00"; // Unicode code for a smiley face
```

**7. String Comparison:**
Strings are compared using lexicographical (dictionary) order.

```jsx
let string1 = "apple";
let string2 = "banana";

console.log(string1 < string2); // Output: true
```

**8. Multiline Strings (ES6):**
Template literals allow you to create multiline strings easily.

```jsx
let multiline = `
  Line 1
  Line 2
  Line 3
`;
```

**9. String Iteration:**
You can iterate through characters in a string using a loop or the `.forEach()` method.

```jsx
let word = "hello";

for (let char of word) {
  console.log(char);
}

word.split("").forEach(function(char) {
  console.log(char);
});

  // prints: 
  // h
  // e
  // l
  // l
  // o
```

# Js Events:

**JavaScript** is considered as an **event-driven language.**

It is designed to respond to events, such as user actions (clicks, typing, etc.), changes in data, or other triggers.

**1. Basic Event Handling:**
You can attach event handlers to elements using JavaScript to respond to various user actions.

```jsx
// Get a reference to an HTML element
let button = document.getElementById("myButton");

// Attach an event handler function
button.addEventListener("click", function() {
  alert("Button clicked!");
});
```

**2. Event Types:**
There are various types of events, such as `click`, `mouseover`, `keydown`, `submit`, etc. Each event type corresponds to a specific user action.

```jsx
element.addEventListener("mouseover", function() {
  console.log("Mouse over the element");
});
```

**3. Event Object:**
When an event occurs, an event object is created with information about the event, such as the target element and event details.

```jsx
element.addEventListener("click", function(event) {
  console.log("Clicked on element: " + event.target.id);
});
```

**4. Event Propagation:**
Events can propagate through the DOM tree, either capturing (from outer to inner elements) or bubbling (from inner to outer elements).

```jsx
// Capture phase
element.addEventListener("click", function() {
  console.log("Capture phase");
}, true);

// Bubbling phase
element.addEventListener("click", function() {
  console.log("Bubbling phase");
}, false);
```

**5. Event Delegation:**
Event delegation is a technique where you attach a single event handler to a parent element, allowing you to handle events for its child elements.

```jsx
// Parent element
let parent = document.getElementById("parent");

// Event delegation for child elements
parent.addEventListener("click", function(event) {
  if (event.target.classList.contains("child")) {
    console.log("Child element clicked");
  }
});
```

**6. Removing Event Listeners:**
You can remove event listeners when they are no longer needed using the `removeEventListener` method.

```jsx
function handleClick() {
  console.log("Button clicked!");
}

button.addEventListener("click", handleClick);

// Later, remove the event listener
button.removeEventListener("click", handleClick);
```

**7. Advanced Event Handling:**
In more complex scenarios, you might need to manage events asynchronously, work with custom events, or handle specific user interactions like drag and drop.

```jsx
// Example: Listening for custom events
document.addEventListener("customEvent", function(event) {
  console.log("Custom event triggered:", event.detail.message);
});

// Trigger a custom event
let customEvent = new CustomEvent("customEvent", {
  detail: { message: "Hello from custom event!" }
});
document.dispatchEvent(customEvent);
```

# Js Numbers:

**1. Numbers:**
Numbers in JavaScript are used to represent numeric values, including integers and floating-point numbers.

```jsx
let age = 25;
let price = 19.99;
```

**2. Arithmetic Operations:**
JavaScript supports various arithmetic operations like addition, subtraction, multiplication, and division.

```jsx
let sum = 5 + 3; // 8
let product = 4 * 6; // 24
```

**3. `Math` Object:**
The `Math` object provides built-in mathematical functions and constants.

```jsx
let circleArea = Math.PI * Math.pow(radius, 2);
let randomNum = Math.random(); // Random number between 0 and 1
```

**4. Rounding Methods:**
The `Math` object has methods for rounding numbers.

- `.ceil()`: Rounds up to the nearest integer.
- `.floor()`: Rounds down to the nearest integer.

```jsx
let roundedUp = Math.ceil(7.3); // 8
let roundedDown = Math.floor(7.8); // 7
```

**5. `Number` Methods:**
The `Number` object has methods for converting strings to numbers and checking numeric properties.

- `.parseInt()`: Converts a string to an integer.
- `.parseFloat()`: Converts a string to a floating-point number.
- `.isNaN()`: Checks if a value is NaN (Not-a-Number).

```jsx
let intValue = Number.parseInt("42"); // 42
let floatValue = Number.parseFloat("3.14"); // 3.14
let isNotANumber = Number.isNaN("hello"); // true
```

**6. `Number.MAX_SAFE_INTEGER` and `Number.MIN_SAFE_INTEGER`:**
JavaScript uses 64-bit floating-point representation for numbers, but sometimes you need larger integers. The largest integer that can be safely represented is `Number.MAX_SAFE_INTEGER`.

**7. `BigInt`:**`BigInt` is a new primitive type introduced to JavaScript for working with arbitrary-precision integers.

```jsx
let bigIntValue = 1234567890123456789012345678901234567890n;
```

**8. BigInt Operations:**`BigInt` supports arithmetic operations similar to regular numbers.

```jsx
let bigSum = bigIntValue + 1n;
let bigProduct = bigIntValue * 2n;
```

**9. Comparing `Number` and `BigInt`:**`BigInt` and regular `Number` are different types, and direct comparisons between them might not work as expected.

```jsx
console.log(123n === 123); // false
```

**10. Converting `BigInt` to `Number`:**
You can convert a `BigInt` to a regular `Number`, but be cautious about potential loss of precision.

```jsx
let bigIntValue = 1234567890123456789012345678901234567890n;
let convertedValue = Number(bigIntValue); // Be careful with large values
```

# Js Math:

**1. Basic Math Functions:**

The `Math` object provides various methods for common mathematical operations:

- `.abs(x)`: Returns the absolute value of `x`.
- `.sqrt(x)`: Returns the square root of `x`.
- `.pow(x, y)`: Returns `x` raised to the power of `y`.
- `.round(x)`: Rounds `x` to the nearest integer.
- `.floor(x)`: Returns the largest integer less than or equal to `x`.
- `.ceil(x)`: Returns the smallest integer greater than or equal to `x`.

```jsx
let absoluteValue = Math.abs(-5); // 5
let squareRoot = Math.sqrt(25); // 5
let power = Math.pow(2, 3); // 8 (2^3)
let roundedNumber = Math.round(4.6); // 5
let floorValue = Math.floor(4.3); // 4
```

**2. Trigonometric Functions:**

`Math` includes trigonometric methods for working with angles:

- `.sin(x)`: Returns the sine of `x` (in radians).
- `.cos(x)`: Returns the cosine of `x` (in radians).
- `.tan(x)`: Returns the tangent of `x` (in radians).

```jsx
let angle = Math.PI / 4; // 45 degrees in radians
let sineValue = Math.sin(angle);
let cosineValue = Math.cos(angle);
let tangentValue = Math.tan(angle);
```

**3. Constants:**

`Math` provides some mathematical constants:

- `Math.PI`: The mathematical constant π (pi).
- `Math.E`: The mathematical constant e (Euler's number).

```jsx
let circleArea = Math.PI * radius * radius;
let exponentialValue = Math.pow(Math.E, 2); // e^2
```

**4. Random Numbers:**

- `.random()`: Returns a random floating-point number between 0 (inclusive) and 1 (exclusive).

```jsx
let randomValue = Math.random(); // Random value between 0 and 1
```

(also helps to generate something random)

**5. Advanced Math Functions:**

`Math` also offers more advanced methods:

- `.log(x)`: Returns the natural logarithm of `x`.
- `.exp(x)`: Returns `e` raised to the power of `x`.

```jsx
let naturalLog = Math.log(10); // ln(10)
let exponentialValue = Math.exp(2); // e^2
```

**6. Advanced Techniques:**

You can combine `Math` methods to perform more complex calculations. For example, to calculate the hypotenuse of a right triangle:

```jsx
function hypotenuse(a, b) {
  return Math.sqrt(Math.pow(a, 2) + Math.pow(b, 2));
}

let result = hypotenuse(3, 4); // 5
```

# Js Loop:

**1. `for` Loop:**

A `for` loop iterates through a block of code a specified number of times.

```jsx
for (let i = 0; i < 5; i++) { // This loop is also known as traditional loop
  console.log(i);
}
```

**2. `while` Loop:**

A `while` loop repeatedly executes a block of code as long as a condition remains true.

```jsx
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

**3. `do...while` Loop:**

A `do...while` loop is similar to a `while` loop, but it executes the block of code at least once, even if the condition is false.

```jsx
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);
```

**4. Loop Control Statements:**

- `break`: Terminates the loop early.
- `continue`: Skips the current iteration and moves to the next.

```jsx
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    break; // Stop the loop when i is 5
  }
  if (i === 3) {
    continue; // Skip the iteration when i is 3
  }
  console.log(i);
}
```

**5. Looping Through Arrays:**

Loops are often used to iterate through arrays.

```jsx
let colors = ["red", "green", "blue"];
for (let color of colors) {
  console.log(color);
}
```

**6. Looping Through Objects:**

You can use loops to iterate through object properties.

```jsx
let person = {
  firstName: "John",
  lastName: "Doe",
  age: 30
};
for (let key in person) {
  console.log(key + ": " + person[key]);
}
```

**7. Nested Loops:**

Loops can be nested within each other to perform complex iterations.

```jsx
for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    console.log(`i: ${i}, j: ${j}`);
  }
}

```

**8. Loop Optimization:**

Avoid unnecessary calculations inside loops to improve performance.

```jsx
// Not optimized
for (let i = 0; i < array.length; i++) {
  // ... do something with array[i]
}

// Optimized
const length = array.length;
for (let i = 0; i < length; i++) {
  // ... do something with array[i]
}
```

**9. Advanced Loop Techniques:**

Loops can be combined with conditional statements and arrays to perform specific tasks efficiently.

```jsx
let numbers = [1, 2, 3, 4, 5];
let sum = 0;
for (let number of numbers) {
  if (number % 2 === 0) {
    sum += number;
  }
}
console.log(sum); // Output: 6 (2 + 4)
```

# Js Dates:

**1. Creating Dates:**

You can create a `Date` object to represent a specific date and time.

```jsx
let currentDate = new Date();
console.log(currentDate);
```

**2. Date Methods:**

`Date` objects have various methods to access and manipulate date components:

```jsx
// Create a new Date object representing the current date and time
const currentDate = new Date();

// 1. getDate(): Returns the day of the month (from 1 to 31)
const dayOfMonth = currentDate.getDate();
// Explanation: Retrieves the day of the month from the Date object.
// Answer: dayOfMonth = current day of the month (e.g., 1, 2, ..., 31)

// 2. getMonth(): Returns the month (from 0 to 11)
const month = currentDate.getMonth();
// Explanation: Retrieves the month from the Date object. Note: Months are zero-based.
// Answer: month = current month (0 for January, 1 for February, ..., 11 for December)

// 3. getFullYear(): Returns the full year (four digits)
const year = currentDate.getFullYear();
// Explanation: Retrieves the full year from the Date object.
// Answer: year = current year (e.g., 2024)

// 4. getHours(), getMinutes(), getSeconds(), getMilliseconds(): Returns the corresponding time components
const hours = currentDate.getHours();
const minutes = currentDate.getMinutes();
const seconds = currentDate.getSeconds();
const milliseconds = currentDate.getMilliseconds();
// Explanation: Retrieves the hours, minutes, seconds, and milliseconds from the Date object.
// hours = current hour (from 0 to 23), minutes = current minute (from 0 to 59),
// seconds = current second (from 0 to 59), milliseconds = current millisecond (from 0 to 999)

// 5. getTime(): Returns the number of milliseconds since January 1, 1970 (Unix timestamp)
const timestamp = currentDate.getTime();
// Explanation: Retrieves the Unix timestamp (number of milliseconds since January 1, 1970) from the Date object.
// Answer: timestamp = current Unix timestamp

// 6. toString(): Converts the Date object to a string representation
const dateString = currentDate.toString();
// Explanation: Converts the Date object to a human-readable string representation.
// Answer: dateString = string representation of the current date and time

// 7. toDateString(): Returns the date portion of the Date object as a human-readable string
const dateOnlyString = currentDate.toDateString();
// Explanation: Converts the Date object to a string containing only the date portion.
// Answer: dateOnlyString = string representation of the current date

// 8. toISOString(): Converts the Date object to a string in ISO format
const isoString = currentDate.toISOString();
// Explanation: Converts the Date object to a string in ISO 8601 format (e.g., "2024-04-01T12:34:56.789Z").
// Answer: isoString = ISO-formatted string representation of the current date and time
```

**3. Formatting Dates:**

JavaScript doesn't have built-in formatting options, but you can create your own or use third-party libraries.

```jsx
let now = new Date();
let formattedDate = `${now.getFullYear()}-${now.getMonth() + 1}-${now.getDate()}`;
console.log(formattedDate); // Output: "2024-4-2" (assuming today is April 2, 2024)
```

**4. Parsing Dates:**

You can parse strings to create `Date` objects using `Date.parse()` or libraries like `moment.js`.

```jsx
let dateString = "2023-08-09";
let parsedDate = new Date(dateString);
console.log(parsedDate); // Output: Thu Aug 09 2023 00:00:00 GMT+0000 (Coordinated Universal Time)
```

**5. Timezones:**

JavaScript's `Date` objects work with the system's time zone. To work with different time zones, you might need external libraries like `luxon` or `date-fns-tz`.

**6. Calculating Time Intervals:**

You can calculate time intervals between dates using the subtraction operator.

```jsx
let startDate = new Date("2023-01-01");
let endDate = new Date("2023-12-31");
let timeDiff = endDate - startDate; // Result in milliseconds
```

**7. Advanced Date Techniques:**

Dates can be complex when considering daylight saving time, leap years, and internationalization. Libraries like `luxon` and `date-fns` provide more advanced date handling features.

**8. Working with Epoch Time:**

Epoch time is the number of milliseconds since January 1, 1970 (UNIX epoch time).

```jsx
let epochTime = Date.now(); // Current epoch time
```

# Js Else If:

**1. Basic `else if` Syntax:**

The basic structure of the `else if` statement looks like this:

```jsx
if (condition1) {
  // Code to execute if condition1 is true
} else if (condition2) {
  // Code to execute if condition2 is true
} else {
  // Code to execute if none of the conditions are true
}
```

**2. Multiple Conditions:**

You can use `else if` to handle different scenarios based on multiple conditions.

```jsx
let score = 85;

if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else if (score >= 70) {
  console.log("C");
} else {
  console.log("F");
}
```

**3. Chaining `else if` Statements:**

You can chain multiple `else if` statements to create more complex conditions.

```jsx
let time = 15;

if (time < 12) {
  console.log("Good morning!");
} else if (time < 18) {
  console.log("Good afternoon!");
} else {
  console.log("Good evening!");
}
```

**4. Using `else if` with Logical Operators:**

You can use logical operators to create more intricate conditions within `else if` statements.

```jsx
let age = 25;
let hasLicense = true;

if (age >= 18 && hasLicense) {
  console.log("You can drive!");
} else if (age >= 16) {
  console.log("You can get a learner's permit.");
} else {
  console.log("You can't drive yet.");
}
```

**5. Nesting `else if` Statements:**

You can also nest `if` and `else if` statements inside each other to handle even more complex conditions.

```jsx
let temperature = 30;
let isSunny = true;

if (temperature > 30) {
  if (isSunny) {
    console.log("It's hot and sunny!");
  } else {
    console.log("It's hot but not sunny.");
  }
} else {
  console.log("The temperature is pleasant.");
}
```

**6. Avoiding Deep Nesting.**

# Js Switch:

**1. Basic `switch` Syntax:**

The basic structure of the `switch` statement looks like this:

```jsx
switch (expression) {
  case value1:
    // Code to execute if expression matches value1
    break;
  case value2:
    // Code to execute if expression matches value2
    break;
  // more cases...
  default:
    // Code to execute if expression doesn't match any case
}
```

**2. Using `switch` with Expressions:**

The expression within the `switch` statement is usually a variable or an expression that you want to compare against various cases.

```jsx
let day = 3;

switch (day) {
  case 1:
    console.log("It's Monday!");
    break;
  case 2:
    console.log("It's Tuesday!");
    break;
  case 3:
    console.log("It's Wednesday!");
    break;
  // ... more cases ...
  default:
    console.log("It's not a weekday.");
}
```

**3. Multiple Cases:**

You can have multiple `case` statements that correspond to the same block of code.

```jsx
let fruit = "apple";

switch (fruit) {
  case "apple":
  case "pear":
  case "banana":
    console.log("It's a fruit!");
    break;
  default:
    console.log("It's not a recognized fruit.");
}
```

**4. No `break` Statement:**

If you omit the `break` statement, execution will "fall through" to the next case.

```jsx
let month = 3;

switch (month) {
  case 1:
    console.log("It's January.");
    // No break here
  case 2:
    console.log("It's February.");
    break;
  default:
    console.log("It's another month.");
}
```

**5. Advanced `switch` Techniques:**

`switch` statements are helpful when you need to compare a single value against multiple possible cases. They provide a cleaner and more concise way to handle these scenarios compared to multiple `if` and `else if` statements.

**6. Use Cases for `switch`:**

`switch` statements are useful when you have a limited number of possible cases and need to perform different actions based on those cases. They are commonly used for menu selection, handling user inputs, and processing different types of data.

**7. When to Use `if` vs. `switch`:**

- Use `if` statements when you have more complex conditions involving comparisons, logical operators, or custom functions.
- Use `switch` statements when you have a single value to compare against multiple fixed cases.

# Js Map:

`Map` objects are commonly used when you need to maintain a collection of key-value pairs and you want to ensure the keys are unique. They're suitable for scenarios such as caching data, managing configuration settings, or storing metadata associated with objects.

**1. Creating a Map:**

You can create a `Map` using the `new Map()` constructor.

```jsx
let myMap = new Map();
```

**2. Adding and Retrieving Values:**

You can use the `set()` method to add key-value pairs to a `Map`.

```jsx
myMap.set("name", "Alice");
myMap.set("age", 30);
```

You can then use the `get()` method to retrieve values based on their keys.

```jsx
console.log(myMap.get("name")); // "Alice"
console.log(myMap.get("age")); // 30
```

**3. Checking Existence:**

The `has()` method allows you to check if a specific key exists in the `Map`.

```jsx
console.log(myMap.has("name")); // true
console.log(myMap.has("address")); // false
```

**4. Removing Entries:**

The `delete()` method is used to remove a specific key-value pair from the `Map`.

```jsx
myMap.delete("age");
console.log(myMap.has("age")); // false
```

**5. Iterating through a Map:**

You can use the `for...of` loop or the `forEach()` method to iterate through the entries of a `Map`.

```jsx
for (let [key, value] of myMap) {
  console.log(`${key}: ${value}`);
}

myMap.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
```

**6. Using Objects as Keys:**

Unlike object properties, `Map` keys can be any data type, including objects.

```jsx
let objKey = { id: 1 };
myMap.set(objKey, "Value associated with an object");
console.log(myMap.get(objKey)); // "Value associated with an object"
```

**7. Advanced Techniques:**

- `Map` objects maintain the order of insertion, which can be beneficial when order matters.
- You can use the `size` property to determine the number of entries in the `Map`.
- The `clear()` method removes all entries from the `Map`.

# Js Throw, and Try...Catch...Finally:

**1. `throw`:**

The `throw` statement is used to manually generate an error or exception.

**Basic Usage:**

```jsx
function divide(a, b) {
  if (b === 0) {
    throw new Error("Division by zero");
  }
  return a / b;
}

try {
  console.log(divide(10, 2)); // 5
  console.log(divide(10, 0)); // Throws an error
} catch (error) {
  console.log("Error:", error.message);
}
```

**2. `try...catch...finally`:**

The `try...catch...finally` statement is used to handle errors in a controlled manner.

**Basic Usage:**

```jsx
try {
  // Code that may cause an error
  console.log("Inside try block");
  throw new Error("Something went wrong");
} catch (error) {
  // Code to handle the error
  console.log("Error:", error.message);
} finally {
  // Code that will run regardless of whether an error occurred
  console.log("Finally block");
}
```

**3. Catching Specific Errors:**

You can catch specific types of errors using multiple `catch` blocks.

```jsx
try {
  // Code that may cause an error
  throw new RangeError("Out of range");
} catch (rangeError) {
  console.log("Range Error:", rangeError.message);
} catch (error) {
  console.log("General Error:", error.message);
}
```

**4. Throwing Custom Errors:**

You can create custom error types by extending the `Error` class.

```jsx
class MyCustomError extends Error {
  constructor(message) {
    super(message);
    this.name = "MyCustomError";
  }
}

try {
  throw new MyCustomError("This is a custom error");
} catch (error) {
  console.log("Error:", error.name, error.message);
}
```

**5. Advanced Techniques:**

- Use `try...catch` to handle synchronous errors. For asynchronous operations, consider using `try...catch` around the `await` expression or the `Promise` handling mechanism.
- The `finally` block is executed regardless of whether an error was thrown or caught.

**6. Use Cases:**

Error handling is crucial for graceful handling of unexpected situations in your code. It helps prevent crashes and provides useful feedback to users or developers when things go wrong. Use `throw` to explicitly raise errors, and use `try...catch...finally` to manage errors and ensure proper cleanup.

# Js Callbacks and Promise:

Callbacks and Promises are key for managing asynchronous operations in JavaScript, like fetching data (like api) or handling user actions. Promises offer a cleaner, more structured approach, and `async/await` further simplifies handling asynchronous code.

**1. Callbacks:**

Callbacks are functions that are passed as arguments to other functions and are executed once the asynchronous operation is complete.

**Basic Callback Example:**

```jsx
function fetchData(callback) {
  setTimeout(() => {
    const data = "Fetched data";
    callback(data);
  }, 1000);
}

function processData(data) {
  console.log("Processed:", data);
}

fetchData(processData); // "Processed: Fetched data"
```

**2. Callback Hell (Callback Pyramid):**

When handling multiple asynchronous operations sequentially, it can lead to nested and hard-to-read code structures known as "Callback Hell."

**Callback Hell Example:**

```jsx
getDataFromServer(function(data) {
  processFirstData(data, function(result1) {
    processResult1(result1, function(finalResult) {
      console.log(finalResult);
    });
  });
});
```

**3. Promises:**

Promises provide a more structured way to handle asynchronous operations by representing a value that may be available now or in the future.

**Basic Promise Example:**

```jsx
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = "Fetched data";
      resolve(data); // Resolving with the fetched data
    }, 1000);
  });
}

fetchData()
  .then(data => {
    console.log("Fetched:", data);
  })
  .catch(error => {
    console.error("Error:", error);
  });
```

**4. Chaining Promises:**

Promises can be chained to handle multiple asynchronous operations sequentially.

Promises have built-in error handling using the `.catch()` method.

**Chaining Promises Example:**

```jsx
fetchData()
  .then(data => processFirstData(data))
  .then(result1 => processResult1(result1))
  .then(finalResult => console.log(finalResult))
  .catch(error => console.error("Error:", error));
```

**5. Async/Await:**

Async functions provide a more readable way to work with Promises, making asynchronous code look more like synchronous code.

**Async/Await Example:**

```jsx
async function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      const data = "Fetched data";
      resolve(data);
    }, 1000);
  });
}

async function processData() {
  try {
    const data = await fetchData();
    console.log("Fetched:", data);
  } catch (error) {
    console.error("Error:", error);
  }
}

processData();
```

**7. Advanced Techniques:**

- Use Promises to avoid callback hell and manage asynchronous operations.
- Combine async/await with Promises for more readable and synchronous-looking asynchronous code.
- Promises can be used for any asynchronous operation, not just HTTP requests.

# Js Hoisting And JSON:

**1. Hoisting:**

Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during compilation. This means you can use variables and functions before they are declared in your code.

**Variable Hoisting:**

```jsx
console.log(myVariable); // undefined
var myVariable = 10;
console.log(myVariable); // 10
```

**Function Hoisting:**

```jsx
myFunction(); // "Hello from myFunction!"
function myFunction() {
  console.log("Hello from myFunction!");
}
```

**2. JSON (JavaScript Object Notation):**

JSON is a lightweight data interchange format that is easy for humans to read and write, and easy for machines to parse and generate. It's widely used for transmitting and storing data between a server and a web application.

**JSON Syntax:**

```json
{
  "name": "Alice",
  "age": 30,
  "isStudent": false,
  "address": {
    "city": "New York",
    "country": "USA"
  },
  "hobbies": ["reading", "painting"]
}
```

**Parsing JSON:**

You can use the `JSON.parse()` method to convert a JSON string into a JavaScript object.

```jsx
let jsonString = '{"name": "Bob", "age": 25}';
let parsedObject = JSON.parse(jsonString);
console.log(parsedObject.name); // "Bob"
```

**Stringifying JSON:**

You can use the `JSON.stringify()` method to convert a JavaScript object into a JSON string.

```jsx
let person = {
  name: "Eve",
  age: 28,
  hobbies: ["coding", "gaming"]
};
let jsonString = JSON.stringify(person);
console.log(jsonString);
```

**Advanced JSON Techniques:**

- JSON supports various data types: objects, arrays, strings, numbers, booleans, and null.
- Nested objects and arrays can be used to structure complex data.
- JSON can be used to store configuration settings, transmit data between client and server, and more.

# Js Class:

Classes are widely used for object-oriented programming in JavaScript, providing a structured and organized way to define and create objects with shared behaviors. They are suitable for modeling real-world entities, organizing code, and improving code maintainability.

**1. Creating a Class:**

The basic structure of a class definition looks like this:

```jsx
class ClassName {
  constructor(/* parameters */) {
    // Constructor code
  }

  /* Methods */
}
```

**2. Constructor:**

The `constructor` method is a special method that gets called when an object is created from the class.

```jsx
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

let person1 = new Person("Alice", 30);
console.log(person1.name); // "Alice"
```

**3. Methods:**

You can define methods inside a class that can be used by objects created from the class.

```jsx
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  calculateArea() {
    return this.width * this.height;
  }
}

let rect = new Rectangle(5, 10);
console.log(rect.calculateArea()); // 50

```

**4. Inheritance:**

Classes can be extended to create subclasses that inherit properties and methods from a parent class.

```jsx
class Square extends Rectangle {
  constructor(sideLength) {
    super(sideLength, sideLength);
  }
}

let square = new Square(4);
console.log(square.calculateArea()); // 16
```

**5. Getters and Setters:**

You can use getter and setter methods to control access to class properties.

```jsx
class Circle {
  constructor(radius) {
    this.radius = radius;
  }

  get diameter() {
    return this.radius * 2;
  }

  set diameter(d) {
    this.radius = d / 2;
  }
}

let circle = new Circle(5);
console.log(circle.diameter); // 10
circle.diameter = 12;
console.log(circle.radius); // 6
```

**6. Static Methods:**

Static methods are methods that are called on the class itself, not on instances of the class.

```jsx
class MathUtils {
  static square(x) {
    return x * x;
  }
}

console.log(MathUtils.square(4)); // 16
```

**7. Advanced Techniques:**

- Classes can encapsulate behavior, making code more organized and reusable.
- You can use classes to create complex data structures, such as linked lists or trees.
- Use `super` to call the parent class's methods or constructor.

# Js OOP:

Object-Oriented Programming (OOP) is a programming paradigm that uses objects to structure code. It helps organize and manage code by modeling real-world entities as objects with properties and behaviors.

**1. Classes and Objects:**

- **Class:** A blueprint for creating objects. It defines the properties (attributes) and methods (behaviors) that objects of that class will have.
- **Object:** An instance of a class. Objects have state (property values) and behavior (methods).

**Basic Class Example:**

```jsx
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Hello, my name is ${this.name}.`);
  }
}

let person1 = new Person("Alice", 30);
let person2 = new Person("Bob", 25);

person1.sayHello(); // "Hello, my name is Alice."
person2.sayHello(); // "Hello, my name is Bob."
```

**2. Inheritance:**

Inheritance allows you to create a new class based on an existing class, inheriting its properties and methods.

**Inheritance Example:**

```jsx
class Student extends Person {
  constructor(name, age, studentId) {
    super(name, age);
    this.studentId = studentId;
  }

  study() {
    console.log(`${this.name} is studying.`);
  }
}

let student = new Student("Eve", 22, "S123");
student.sayHello(); // "Hello, my name is Eve."
student.study(); // "Eve is studying."
```

**3. Encapsulation:**

Encapsulation is the idea of bundling data (properties) and methods (functions) that operate on the data into a single unit (object).

**Encapsulation Example:**

```jsx
class BankAccount {
  constructor(accountNumber, balance) {
    this.accountNumber = accountNumber;
    this.balance = balance;
  }

  deposit(amount) {
    this.balance += amount;
  }

  withdraw(amount) {
    if (amount <= this.balance) {
      this.balance -= amount;
    } else {
      console.log("Insufficient funds.");
    }
  }

  getBalance() {
    return this.balance;
  }
}

let account = new BankAccount("A12345", 1000);
account.deposit(500);
account.withdraw(200);
console.log(account.getBalance()); // 1300

```

**4. Polymorphism:**

Polymorphism allows objects of different classes to be treated as objects of a common superclass, enabling dynamic behavior based on the actual object type.

**Polymorphism Example:**

```jsx
class Shape {
  area() {
    console.log("Calculating area of a shape.");
  }
}

class Circle extends Shape {
  constructor(radius) {
    super();
    this.radius = radius;
  }

  area() {
    return Math.PI * this.radius * this.radius;
  }
}

class Rectangle extends Shape {
  constructor(width, height) {
    super();
    this.width = width;
    this.height = height;
  }

  area() {
    return this.width * this.height;
  }
}

function calculateArea(shape) {
  console.log(`Area: ${shape.area()}`);
}

let circle = new Circle(5);
let rectangle = new Rectangle(4, 6);

calculateArea(circle); // Area: 78.53981633974483
calculateArea(rectangle); // Area: 24
```

**5. Advanced OOP Techniques:**

- **Composition:** Building complex objects by combining simpler objects as properties.
- **Interfaces and Abstract Classes:** Defining common behavior without providing implementation details.
- **Design Patterns:** Reusable solutions for common programming challenges.

# Js DOM:

The Document Object Model (DOM) is a crucial concept in web development that represents the structure of an HTML document as a tree of objects. It enables JavaScript to interact with and manipulate the content and structure of a web page. Let's explore the DOM from the basics to more advanced usage:

**1. Basic DOM Manipulation:**

**Accessing Elements**

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 id="title">Hello, DOM!</h1>
    <p class="content">This is a paragraph.</p>
    <button id="myButton">Click Me</button>
    <form>
      <input type="text" />
    </form>
  </body>
</html>
```

```jsx
// By ID, class, tag, or query selectors
const title = document.getElementById("title");
const paragraphs = document.getElementsByClassName("content");
const button = document.querySelector("#myButton");
const allParagraphs = document.querySelectorAll("p");
```

---

**Modifying Elements**

```jsx
// Text and attributes
title.textContent = "Updated Title";
paragraphs[0].textContent = "Modified paragraph.";
button.disabled = true;

// CSS styles
title.style.color = "red";
paragraphs[0].style.fontSize = "16px";
```

---

**Event Handling**

```jsx
// Click event
button.addEventListener("click", () => {
  alert("Button clicked!");
});

// Keydown event
document.querySelector('input[type="text"]').addEventListener("keydown", (event) => {
  console.log("Key pressed:", event.key);
});

// Preventing form submission
document.querySelector("form").addEventListener("submit", (event) => {
  event.preventDefault();
  console.log("Form submission prevented");
});
```

---

**Creating and Appending Elements**

```jsx
const newDiv = document.createElement("div");
newDiv.className = "new-class";
newDiv.textContent = "This is a new div.";
document.body.appendChild(newDiv);
```

---

**Removing Elements**

```jsx
document.body.removeChild(newDiv);
```

---

**Traversing the DOM**

```jsx
// Parent and child navigation
const parent = title.parentNode;
const child = parent.children[0];
const sibling = child.nextElementSibling;

// Query selectors
const firstParagraph = document.querySelector("p");
```

### **JavaScript DOM Methods & Usage**

**Element Selection**

1. **`querySelector`** - Finds the *first* element matching a CSS selector.
2. **`querySelectorAll`** - Finds *all* elements matching a CSS selector.
3. **`getElementById`** - Gets an element by its unique ID.
4. **`getElementsByClassName`** - Gets all elements with a specific class name.
5. **`getElementsByTagName`** - Gets all elements with a specific HTML tag name.

**Element Creation & Manipulation**

1. **`createElement`** - Creates a new HTML element.
2. **`appendChild`** - Appends a new child element.
3. **`removeChild`** - Removes a child element.
4. **`setAttribute`** - Sets an attribute’s value.
5. **`getAttribute`** - Gets an attribute’s value.
6. **`classList`** - Manages CSS classes (`add`, `remove`, `toggle`).
7. **`style`** - Sets inline CSS styles.
8. **`innerHTML`** - Sets or gets HTML content.
9. **`innerText`** - Sets or gets text content.
10. **`cloneNode`** - Creates a copy of a node (with optional deep clone).

**Parent/Child Navigation**

1. **`parentNode`** - Gets the parent element.
2. **`childNodes`** - Gets all child nodes, including text and comments.
3. **`children`** - Gets only element children.
4. **`closest`** - Finds the closest ancestor that matches a selector.
5. **`nextElementSibling`** - Gets the next sibling element.
6. **`previousElementSibling`** - Gets the previous sibling element.

**Scrolling & Focus**

1. **`scrollIntoView`** - Scrolls an element into view.
2. **`focus`** - Sets focus on an element.
3. **`blur`** - Removes focus from an element.

**Event Handling**

1. **`addEventListener`** - Attaches an event listener to an element.
2. **`dispatchEvent`** - Triggers a specified event.

---

### **JavaScript Event Listeners**

**Mouse Events**

- **`click`** - Single click.
- **`dblclick`** - Double click.
- **`mousedown`** / **`mouseup`** - Pressing / releasing mouse button.
- **`mouseenter`** / **`mouseleave`** - Mouse enters or leaves an element (does not trigger on child elements).
- **`mouseover`** / **`mouseout`** - Similar to `mouseenter` and `mouseleave`, but includes child elements.
- **`mousemove`** - Detects mouse movement over an element.

**Keyboard Events**

- **`keydown`** / **`keyup`** - Key pressed / released.
- **`keypress`** - Key is being pressed.

**Form Events**

- **`submit`** - Form submission.
- **`focus`** / **`blur`** - Field gains or loses focus.
- **`input`** - Fires when the input value changes.
- **`cut`** / **`paste`** - Fires when text is cut/pasted.

**Preventing Default Actions**

- **`event.preventDefault()`** - Stops the default browser behavior (e.g., prevents form from submitting or link from opening).

---

# **References**

1. [w3school](https://www.w3schools.com/js/default.asp)
2. [Learn with Sumit Js course](https://youtube.com/playlist?list=PLHiZ4m8vCp9OkrURufHpGUUTBjJhO9Ghy&si=fCi19TArZQlBq6i0)
3. [JavaScript HTML DOM Events](https://www.w3schools.com/js/js_htmldom_events.asp)
4. [HTML DOM Events](https://www.w3schools.com/jsref/dom_obj_event.asp)
5. Helped to organize “Chatgpt”