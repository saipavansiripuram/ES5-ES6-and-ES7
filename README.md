# JavaScript ES5 ,ES6 and ES7 Features



### 1. Strict Mode
Strict mode enforces stricter parsing and error handling.

**Example:**
```javascript
'use strict';
x = 3.14; // Throws a ReferenceError because x is not declared
```

### 2. JSON Support
Native support for parsing and serializing JSON data.

**Example:**
```javascript
var jsonStr = '{"name": "Alice", "age": 30}';
var obj = JSON.parse(jsonStr);
console.log(obj.name); // Output: Alice
```

### 3. Array Methods
New methods for arrays like `forEach`, `map`, `filter`, `reduce`, etc.

**Example:**
```javascript
var numbers = [1, 2, 3];
numbers.forEach(function(number) {
  console.log(number);
});
// Output: 1, 2, 3
```

### 4. Object Methods
New methods for objects like `Object.create`, `Object.keys`, etc.

**Example:**
```javascript
var person = { name: "Alice", age: 30 };
var keys = Object.keys(person);
console.log(keys); // Output: ["name", "age"]
```

### 5. Getter and Setter Functions
Define getters and setters for object properties.

**Example:**
```javascript
var person = {
  firstName: "Alice",
  lastName: "Johnson",
  get fullName() {
    return this.firstName + " " + this.lastName;
  },
  set fullName(name) {
    var parts = name.split(" ");
    this.firstName = parts[0];
    this.lastName = parts[1];
  }
};

console.log(person.fullName); // Output: Alice Johnson
person.fullName = "Bob Smith";
console.log(person.firstName); // Output: Bob
console.log(person.lastName); // Output: Smith
```

## ES6 (2015) Key Features

### 1. `let` and `const` Keywords
Block-scoped variable declarations with `let` and constants with `const`.

**Example:**
```javascript
let x = 10;
const PI = 3.14;
```

### 2. Arrow Functions
Shorter syntax for writing function expressions.

**Example:**
```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // Output: 5
```

### 3. Template Literals
Strings enclosed in backticks that allow embedded expressions.

**Example:**
```javascript
const name = 'Alice';
const greeting = `Hello, ${name}!`;
console.log(greeting); // Output: Hello, Alice!
```

### 4. Destructuring
Extract values from arrays or properties from objects into distinct variables.

**Example:**
```javascript
const person = { name: 'Alice', age: 30 };
const { name, age } = person;
console.log(name); // Output: Alice
console.log(age); // Output: 30
```

### 5. Default Parameters
Function parameters with default values.

**Example:**
```javascript
function greet(name = 'Guest') {
  return `Hello, ${name}!`;
}
console.log(greet()); // Output: Hello, Guest!
console.log(greet('Alice')); // Output: Hello, Alice!
```

### 6. Rest and Spread Operators
Rest operator for variable number of arguments and spread operator for expanding arrays.

**Example:**
```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3)); // Output: 6

const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); // Output: [1, 2, 3, 4, 5]
```

### 7. Classes
Syntactical sugar over JavaScript's existing prototype-based inheritance.

**Example:**
```javascript
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
  get area() {
    return this.height * this.width;
  }
}

const rect = new Rectangle(10, 5);
console.log(rect.area); // Output: 50
```

### 8. Modules
Native support for modules with `import` and `export` statements.

**Example:**
```javascript
// In a file named `math.js`
export function add(a, b) {
  return a + b;
}

// In another file
import { add } from './math.js';
console.log(add(2, 3)); // Output: 5
```

### 9. Promises
A cleaner alternative to callbacks for handling asynchronous operations.

**Example:**
```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    // Async operation, e.g., fetching data from a server
    if (success) {
      resolve(data);
    } else {
      reject(error);
    }
  });
}

fetchData()
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

### 10. Symbol Data Type
A new primitive data type for unique identifiers.

**Example:**
```javascript
const sym1 = Symbol('description');
const sym2 = Symbol('description');
console.log(sym1 === sym2); // Output: false
```

## ES7 (2016) Key Features

### 1. `Array.prototype.includes()`
Determines whether an array includes a certain value.

**Example:**
```javascript
const numbers = [1, 2, 3];
console.log(numbers.includes(2)); // Output: true
console.log(numbers.includes(4)); // Output: false
```

### 2. Exponentiation Operator
A shorthand for exponentiation using `**`.

**Example:**
```javascript
console.log(2 ** 3); // Output: 8
```


## ES8 (2017) Key Features

### 1. `Object.values()`
Returns an array of a given object's own enumerable property values.

**Example:**
```javascript
const obj = { a: 1, b: 2, c: 3 };
console.log(Object.values(obj)); // Output: [1, 2, 3]
```

### 2. `Object.entries()`
Returns an array of a given object's own enumerable property `[key, value]` pairs.

**Example:**
```javascript
const obj = { a: 1, b: 2, c: 3 };
console.log(Object.entries(obj)); // Output: [['a', 1], ['b', 2], ['c', 3]]
```

### 3. String Padding
`padStart()` and `padEnd()` methods for strings.

**Example:**
```javascript
console.log('5'.padStart(2, '0')); // Output: '05'
console.log('5'.padEnd(2, '0')); // Output: '50'
```

### 4. `Object.getOwnPropertyDescriptors()`
Returns all own property descriptors of a given object.

**Example:**
```javascript
const obj = { a: 1, b: 2 };
const descriptors = Object.getOwnPropertyDescriptors(obj);
console.log(descriptors);
// Output: { a: { value: 1, writable: true, enumerable: true, configurable: true }, b: { value: 2, writable: true, enumerable: true, configurable: true } }
```

### 5. Trailing Commas in Function Parameter Lists and Calls
Allows trailing commas in function parameter lists and calls.

**Example:**
```javascript
function foo(
  param1,
  param2,
) {
  // do something
}

foo(
  'value1',
  'value2',
);
```

### 6. `async`/`await`
Asynchronous functions that work with Promises, providing a cleaner syntax for asynchronous code.

**Example:**
```javascript
async function fetchData() {
  try {
    let response = await fetch('https://api.example.com/data');
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

## ES9 (2018) Key Features

### 1. `async` Iteration
Enables the use of `for await...of` loops to iterate over async iterables.

**Example:**
```javascript
async function process(array) {
  for await (let value of array) {
    console.log(value);
  }
}

const asyncIterable = {
  [Symbol.asyncIterator]: async function* () {
    yield 'Hello';
    yield 'Async';
    yield 'Iteration';
  }
};

process(asyncIterable); // Output: Hello Async Iteration
```

