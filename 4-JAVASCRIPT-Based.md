<h1 align="center">JAVASCRIPT SCRIPT</h1>

# Table of Contents

1. [What is JavaScript and where does it run?](#1-what-is-javascript-and-where-does-it-run)
2. [Explain var, let, and const](#2-explain-var-let-and-const)
3. [What is hoisting in JavaScript?](#3-what-is-hoisting-in-javascript)
4. [What are data types in JavaScript?](#4-what-are-data-types-in-javascript)
5. [Explain == vs ===](#5-explain--vs-)
6. [What is type coercion?](#6-what-is-type-coercion)
7. [What are functions? Explain function types](#7-what-are-functions-explain-function-types)
8. [Difference between arrow function and normal function](#8-difference-between-arrow-function-and-normal-function)
9. [What is this keyword?](#9%EF%B8%8F⃣-what-is-the-this-keyword)
10. [Explain call, apply, and bind](#10-explain-call-apply-and-bind)
11. [What are closures?](#1%EF%B8%8F⃣1%EF%B8%8F⃣-what-are-closures)
12. [What is scope and scope chain?](#1%EF%B8%8F⃣2%EF%B8%8F⃣-what-is-scope-and-scope-chain)
13. [Explain synchronous vs asynchronous JavaScript](#1%EF%B8%8F⃣3%EF%B8%8F⃣-explain-synchronous-vs-asynchronous-javascript)
14. [What is the Event Loop?](#1%EF%B8%8F⃣4%EF%B8%8F⃣-what-is-the-event-loop)
15. [Explain setTimeout, setImmediate, Promise.then](#1%EF%B8%8F⃣5%EF%B8%8F⃣-explain-settimeout-setimmediate-promisethen)
16. [What are promises?](#1%EF%B8%8F⃣6%EF%B8%8F⃣-what-are-promises)
17. [Explain async/await](#1%EF%B8%8F⃣7%EF%B8%8F⃣-explain-asyncawait)
18. [How does error handling work in JavaScript?](#1%EF%B8%8F⃣8%EF%B8%8F⃣-how-does-error-handling-work-in-javascript)
19. [What are objects in JavaScript?](#1%EF%B8%8F⃣9%EF%B8%8F⃣-what-are-objects-in-javascript)
20. [What is destructuring?](#2%EF%B8%8F⃣0%EF%B8%8F⃣-what-is-destructuring)
21. [Explain spread (...) and rest operator](#2%EF%B8%8F⃣1%EF%B8%8F⃣-explain-spread--and-rest-operator)
22. [What are arrays and common array methods?](#2%EF%B8%8F⃣2%EF%B8%8F⃣-what-are-arrays-and-common-array-methods)
23. [What is shallow copy vs deep copy?](#2%EF%B8%8F⃣3%EF%B8%8F⃣-what-is-shallow-copy-vs-deep-copy)
24. [Explain prototypes and prototypal inheritance](#2%EF%B8%8F⃣4%EF%B8%8F⃣-explain-prototypes-and-prototypal-inheritance)
25. [What is ES6+ and why is it important?](#2%EF%B8%8F⃣5%EF%B8%8F⃣-what-is-es6-and-why-is-it-important)
26. [Debouncing-Throttle](#2%EF%B8%8F⃣6%EF%B8%8F⃣-debouncing--throttling)
27. [What-is-TDZ](#2%EF%B8%8F⃣7%EF%B8%8F⃣-what-is-tdz)


## 1. What is JavaScript and where does it run?

JavaScript is a high-level, interpreted, and dynamic programming language that is primarily used to create interactive web pages.

It can run:
- In the browser (using JavaScript engines like V8, SpiderMonkey)
- On the server side using the Node.js runtime environment

---

## 2. Explain var, let, and const

### var
- Function-scoped
- Can be redeclared and reassigned
- Hoisted and initialized with undefined
- Initialization is optional

### let
- Block-scoped
- Can be reassigned but cannot be redeclared
- Hoisted but exists in the Temporal Dead Zone (TDZ)
- Initialization is optional

### const
- Block-scoped
- Cannot be reassigned and cannot be redeclared
- Hoisted but exists in the TDZ
- Initialization is mandatory

---

## 3. What is hoisting in JavaScript?

Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their scope during the compilation phase before code execution.

- `var` is hoisted and initialized with `undefined`
- `let` is hoisted but remains in the Temporal Dead Zone
- `const` is also hoisted but remains in the TDZ
- Function declarations are fully hoisted (both name and body)
- In function expressions, only the variable is hoisted, not the function body

---

## 4. What are data types in JavaScript?

Data types define what kind of value a variable can hold.

JavaScript has two types of data types:

### Primitive Data Types
- Immutable
- Stored by value
- String, Number, Boolean, null, undefined

### Non-Primitive (Reference) Data Types
- Mutable
- Stored by reference
- Object, Array, Function

---

## 5. Explain `==` vs `===`

### `==` (Loose Equality)
- Compares only values, not types
- Performs implicit type conversion
- Can cause unexpected results  
  *Example:* `"" == 0` → `true`

### `===` (Strict Equality)
- Compares both value and type
- No implicit type conversion
- Prevents unexpected errors

---

## 6. What is type coercion?

Type coercion is the process of converting one data type into another, either automatically or manually.

### Types:
- **Implicit Type Coercion:** JavaScript automatically converts the type  
  *Example:* `'2' * 5` → `10`
- **Explicit Type Coercion:** Developer manually converts the type  
  *Using:* `String()`, `Number()`, `Boolean()`, `parseInt()`, `parseFloat()`
---

## 7. What are functions? Explain function types

A function is a reusable block of code that performs a specific task. Functions help in code reusability, readability, and modularity.

### Function Types in JavaScript

#### 1️⃣ Function Declaration
- A function defined using the `function` keyword with a name.

#### 2️⃣ Function Expression
- A function assigned to a variable.

#### 3️⃣ Arrow Function
- A shorter syntax for writing functions using `=>`.


#### 4️⃣ Anonymous Function
- A function without a name, usually used as a callback.
---  

## 8. Difference between Arrow Function and Normal Function

Arrow functions and normal functions differ in how they handle `this`, `arguments`, constructors, and syntax.

| Feature               | Normal Function                         | Arrow Function                                    |
|------------------------|----------------------------------------|--------------------------------------------------|
| `this` keyword        | Has its own `this` (depends on how it is called) | Does not have its own `this`; inherits from parent scope |
| Arguments object      | Has its own arguments object          | Does not have `arguments`                       |
| Constructor usage     | Can be used as a constructor with `new` | Cannot be used as a constructor               |
| Hoisting              | Function declarations are hoisted     | Not hoisted                                    |
| Syntax                | Longer syntax                         | Shorter and cleaner syntax                    |

---

## 9️⃣ What is the `this` keyword?

The `this` keyword refers to the object that is currently calling the function. Its value depends on how and where the function is called, not where it is written.
such as global scope, function call, object method, or arrow function.

---

## 10. Explain call, apply, and bind

`call`, `apply`, and `bind` are methods used to manually set the value of `this` for a function.

- **call()**: Invokes the function immediately with a specified `this` value and arguments.
- **apply()**: Same as `call()`, but arguments are passed as an array.
- **bind()**: Returns a new function with permanently bound `this` ,,without invoking it immediately.

**Usage:**  
- `bind` is often used in event handlers and callbacks.
- `call` and `apply` are useful for function borrowing(`where one object canuse a method of another object`) or immediately invoking functions with a specific context.
---

## 1️⃣1️⃣ What are closures?

A closure is created when a function remembers and can access variables from its outer (lexical) scope even after the outer function has finished executing.

**Uses**:  
- Data hiding  
- Encapsulation

---

## 1️⃣2️⃣ What is scope and scope chain?

### Scope
Determines where a variable can be accessed in a program. It defines the visibility and lifetime of variables.

### Types of Scope

- **Global Scope**  
  Variables declared outside any function or block.  
  Accessible from anywhere in the program.

- **Local (Function) Scope**  
  Variables declared inside a function.  
  Accessible only within that function.

- **Block Scope**  
  Variables declared with `let` and `const` inside `{ }`.  
  Accessible only inside that block.

---

### Lexical Environment
A structure that stores variable bindings.  
Created when code is written, not executed.  
Each environment has a reference to its outer (parent) environment.

---

### What is Scope Chain?
Scope Chain is a process by which JavaScript look up for a variables:

- Search in the current scope
- If not found, move to the outer scope
- Continue until the global scope
- If not found, throw a `ReferenceError`

---

## 1️⃣3️⃣ Explain synchronous vs asynchronous JavaScript

- **Synchronous JavaScript**  
  Executes code line by line and blocks subsequent code until a task completes.

- **Asynchronous JavaScript**  
  Allows long-running operations to execute without blocking the main thread.  
  While these tasks run in the background, JavaScript continues executing other code. Once the operation completes, the result is handled using callbacks,
  promises, or async/await.

---

## 1️⃣4️⃣ What is the Event Loop?

The Event Loop enables JavaScript to perform non-blocking asynchronous operations, despite being single-threaded.

**How it works**:
- Executes synchronous code in the call stack.
- Asynchronous tasks are handled by Web APIs or Node APIs, with callbacks placed in the task queues.
- When the call stack is empty:
  - The event loop moves tasks from the microtask queue (promises, `queueMicrotask`) to the call stack.
  - Then processes tasks from the macrotask queue (`setTimeout`, `setInterval`, events).

---

## 1️⃣5️⃣ Explain `setTimeout`, `setImmediate`, `Promise.then`

- **`setTimeout`**  
  Executes code after a minimum delay.  
  Callback goes to the **macrotask queue**.  
  Delay is not guaranteed; depends on the event loop.

- **`setImmediate`** (Node.js only)  
  Executes code after the current event loop phase.  
  Callback goes to the **macrotask queue**.  
  Usually runs before `setTimeout(0)` in Node.js.

- **`Promise.then`**  
  Executes after the promise is resolved.  
  Callback goes to the **microtask queue**.  
  Always executes before macrotasks.
---

## 1️⃣6️⃣ What are promises?

A Promise is an object that represents the eventual completion or failure of an asynchronous operation. It helps to write async code in a more readable and manageable way compared to callbacks.

### 🔹 Promise States

A promise can be in one of three states:

- **Pending**
  - Initial state
  - Operation is still in progress

- **Fulfilled**
  - Operation completed successfully
  - Returns a value

- **Rejected**
  - Operation failed
  - Returns an error

### 🔹 Methods

- **.then()**
  - Used to handle the fulfilled state

- **.catch()**
  - Used to handle the rejected state

- **.finally()**
  - Executes regardless of success or failure

---

## 1️⃣7️⃣ Explain async/await

`async/await` is a modern syntax built on top of promises that allows writing asynchronous code in a cleaner, more readable, and synchronous-like manner.

### 🔹 async
- Makes a function return a promise

### 🔹 await
- Pauses execution until the promise resolves or rejects

---

## 1️⃣8️⃣ How does error handling work in JavaScript?

Error handling in JavaScript is the mechanism used to detect and manage runtime and asynchronous errors using `try...catch`, promise rejection handling, and custom errors, ensuring applications do not crash and can fail gracefully.

---

## 1️⃣9️⃣ What are objects in JavaScript?

An object is a collection of key–value pairs used to store related data and behavior together. They help represent real-world entities and organize data efficiently.

- Can be created using object literal or `new Object()`
- Properties can be accessed using dot or bracket notation
- Objects are mutable
- Stored and passed by reference, not by value

---

## 2️⃣0️⃣ What is destructuring?

Destructuring is a JavaScript feature that allows extracting values from arrays or objects and assigning them to variables in a shorter and cleaner way.

---

## 2️⃣1️⃣ Explain Spread (...) and Rest Operator

### 🔹 Spread Operator (...)

The spread operator (`...`) is used to expand elements of an array or object into individual values.  
**Common Uses:**  
- Copy arrays or objects  
- Combine arrays or objects  


### 🔹 Rest Operator (...)

The rest operator (`...`) collects multiple values into a single array or object.  
**Common Uses:**  
- Function parameters to handle variable number of arguments
---

## 2️⃣2️⃣ What are arrays and common array methods?

### Arrays
An array is an ordered collection of values stored in a single variable.  
- Values can be of the same or different data types  
- Accessed via index (starting at 0)

### Common Array Methods (Very Important for Interviews)

1. **push() / pop()**  
   - `push()`: Adds element at the end  
   - `pop()`: Removes element from the end

2. **unshift() / shift()**  
   - `unshift()`: Adds element at the start  
   - `shift()`: Removes element from the start

3. **map()**  
   - Creates a new array by transforming each element

4. **filter()**  
   - Creates a new array with elements that match a condition

5. **reduce()**  
   - Reduces array to a single value (e.g., sum, product)

6. **forEach()**  
   - Iterates over array elements (does not return a new array)

---

## 2️⃣3️⃣ What is shallow copy vs deep copy?

### 🔹 Shallow Copy
- Creates a new object/array, but nested objects are shared the same reference
- Changes in nested objects affect the original

```javascript
const obj1 = { a: 1, nested: { b: 2 } };
const obj2 = { ...obj1 }; // Shallow copy
obj2.nested.b = 3;  
console.log(obj1.nested.b); // 3 (affected)
```

### 🔹 Deep Copy
- Creates a new object/array including all the nested object
- Changes in nested objects do not affect the original

```javascript
const obj1 = { a: 1, nested: { b: 2 } };
const obj2 = structuredClone(obj1); // Deep copy
obj2.nested.b = 3;  
console.log(obj1.nested.b); // 2 (unaffected)
```

---

## 2️⃣4️⃣ Explain prototypes and prototypal inheritance

### 🔹 What is a Prototype?
- In JavaScript, each object has an internal property called `[[Prototype]]` (accessible via `__proto__`)
- It points to another object from which it can inherit properties and methods

### 🔹 Prototypal Inheritance
- Allows one object to use properties and methods of another object
- Enables object-based inheritance without classes

```javascript
const parent = { greet() { return "Hello"; } };
const child = Object.create(parent);
console.log(child.greet()); // "Hello"
```

---

## 2️⃣5️⃣ What is ES6+ and why is it important?

- ES6+ refers to ECMAScript 2015 and later versions
- which introduced modern features to make JavaScript more powerful, readable, and maintainable.

### 🔹 Key ES6+ Features:
- **let / const:** Block-scoped variables  
- **Arrow Functions:** Shorter function syntax  
- **Modules (import/export):** Modular code organization  
- **Promises:** Better asynchronous handling  
- **Classes:** Cleaner syntax for inheritance and object creation
---

## 2️⃣6️⃣ Debouncing & Throttling

### 🔹 Debouncing
Ensures a function is executed only after a specified delay since the last event.  
Useful for limiting the rate of function calls, e.g., search input


### 🔹 Throttling
Ensures a function runs at most once every specified interval, regardless of how often the event occurs.  
Useful for scroll events, resize, etc.

---
## 2️⃣7️⃣ What is TDZ

- TDZ (Temporal Dead Zone) is the period between the start of a block and the declaration of a let or const variable, during which the variable cannot be accessed
  
---
<h1 align="center" red>LET ROCK....</h1>
