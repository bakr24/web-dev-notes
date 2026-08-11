# JavaScript Functions

A function is a reusable block of code designed to perform a specific task.

---

## 1. Function Declaration

```js
function greet() {
    console.log("Hello");
}

greet();
```

A function can be called multiple times:

```js
greet();
greet();
```

---

## 2. Parameters and Arguments

**Parameters** are variables defined by the function.

**Arguments** are the actual values passed to it.

```js
function greet(name) {
    console.log("Hello " + name);
}

greet("Abubakar");
```

Here:

```text
name      → parameter
"Abubakar" → argument
```

---

## 3. Return

`return` sends a value back from the function.

```js
function add(a, b) {
    return a + b;
}

const result = add(5, 3);

console.log(result); // 8
```

After `return`, the function stops executing.

```js
function test() {
    return "Done";

    console.log("Never runs");
}
```

---

## 4. Default Parameters

Provides a default value when an argument isn't supplied.

```js
function greet(name = "Guest") {
    console.log(`Hello ${name}`);
}

greet(); // Hello Guest
```

---

## 5. Function Expression

A function can be stored inside a variable.

```js
const greet = function () {
    console.log("Hello");
};

greet();
```

Function expressions can be anonymous.

---

## 6. Arrow Functions

Shorter syntax for functions.

```js
const add = (a, b) => {
    return a + b;
};
```

For a single expression, you can omit `{}` and `return`:

```js
const add = (a, b) => a + b;
```

Single parameter:

```js
const square = x => x * x;
```

No parameters:

```js
const greet = () => console.log("Hello");
```

---

## 7. Callback Functions

A function passed to another function is called a **callback**.

```js
function processUser(name, callback) {
    callback(name);
}

processUser("Abubakar", function (name) {
    console.log(`Hello ${name}`);
});
```

Common examples:

```js
[1, 2, 3].forEach(() => {});
```

---

## 8. Higher-Order Functions

A function that:

* accepts another function, or
* returns another function

is a **higher-order function**.

Example:

```js
function calculate(a, b, operation) {
    return operation(a, b);
}

const result = calculate(5, 3, (a, b) => a + b);

console.log(result); // 8
```

---

## 9. Rest Parameters

Collects multiple arguments into an array.

```js
function sum(...numbers) {
    return numbers.reduce((total, number) => total + number, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

`...numbers` is a **rest parameter**.

---

## 10. Scope

Variables declared inside a function are normally accessible only inside that function.

```js
function test() {
    const message = "Hello";

    console.log(message);
}

test();

// console.log(message); // Error
```

JavaScript has:

* Global scope
* Function scope
* Block scope

`let` and `const` are block-scoped.

---

## 11. Function Hoisting

Function declarations can be called before they are written.

```js
greet();

function greet() {
    console.log("Hello");
}
```

But function expressions and arrow functions assigned to `const` cannot be used before initialization.

```js
// greet(); // Error

const greet = () => {
    console.log("Hello");
};
```

---

## 12. Pure Functions

A pure function:

* produces the same output for the same input
* doesn't modify outside state

```js
function add(a, b) {
    return a + b;
}
```

Pure functions are easier to test and maintain.

---

## Common Mistakes

### Forgetting `return`

```js
function add(a, b) {
    a + b;
}
```

This returns `undefined`.

Correct:

```js
function add(a, b) {
    return a + b;
}
```

### Confusing parameters and arguments

```js
function greet(name) { } // parameter

greet("Ali");             // argument
```

### Calling a function without required data

```js
function add(a, b) {
    return a + b;
}

add(5); // 5 + undefined → NaN
```

---

## Quick Revision

```text
Function declaration
Function expression
Arrow function
Parameters
Arguments
return
Default parameters
Callback
Higher-order function
Rest parameters
Scope
Hoisting
Pure functions
```

### Main Idea

```text
Input → Function → Output
```

Functions help make code:

* Reusable
* Organized
* Maintainable
* Easier to test
