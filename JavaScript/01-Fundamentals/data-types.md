# JavaScript Data Types

JavaScript data types define what kind of value a variable contains.

JavaScript is **dynamically typed**, meaning a variable can hold different types of values during execution.

```js
let value = 10;

value = "Hello";
value = true;
```

---

## 1. Primitive Data Types

JavaScript has **7 primitive types**:

| Type      | Example        |
| --------- | -------------- |
| String    | `"Hello"`      |
| Number    | `25`           |
| BigInt    | `123n`         |
| Boolean   | `true`         |
| Undefined | `undefined`    |
| Null      | `null`         |
| Symbol    | `Symbol("id")` |

### String

Used for text.

```js
const name = "Abubakar";
```

### Number

Used for integers and decimals.

```js
const age = 22;
const price = 99.99;
```

Special numbers:

```js
Infinity
NaN
```

### Boolean

Only two values:

```js
true
false
```

Commonly used in conditions.

```js
const isLoggedIn = true;
```

### Undefined

A variable exists but has not been assigned a value.

```js
let username;

console.log(username); // undefined
```

### Null

Represents an intentional absence of a value.

```js
let user = null;
```

### BigInt

Used for very large integers.

```js
const bigNumber = 12345678901234567890n;
```

### Symbol

Creates a unique value.

```js
const id = Symbol("id");
```

---

## 2. Non-Primitive / Reference Types

The main non-primitive type is **Object**.

Examples:

```js
const user = {
    name: "Abubakar",
    age: 22
};

const numbers = [1, 2, 3];

function greet() {
    console.log("Hello");
}
```

Objects include:

* Objects
* Arrays
* Functions
* Dates
* Maps
* Sets

---

## 3. `typeof`

Use `typeof` to check a value's type.

```js
typeof "Hello";     // "string"
typeof 25;          // "number"
typeof true;        // "boolean"
typeof undefined;   // "undefined"
typeof 10n;         // "bigint"
typeof Symbol();    // "symbol"
typeof {};          // "object"
```

### Important quirks

```js
typeof null;  // "object"
typeof [];    // "object"
typeof NaN;   // "number"
```

For arrays, use:

```js
Array.isArray([]);
```

Result:

```js
true
```

---

## 4. Primitive vs Reference

Primitive values are copied independently:

```js
let a = 10;
let b = a;

b = 20;

console.log(a); // 10
```

Objects are reference-based:

```js
const user1 = { name: "Abubakar" };
const user2 = user1;

user2.name = "Ali";

console.log(user1.name); // Ali
```

Both variables refer to the same object.

---

## 5. Type Conversion

JavaScript can convert values between types.

### String

```js
String(100); // "100"
```

### Number

```js
Number("100"); // 100
```

### Boolean

```js
Boolean(1); // true
Boolean(0); // false
```

---

## 6. Type Coercion

JavaScript can automatically convert types.

```js
"5" + 2; // "52"
"5" - 2; // 3
```

This is called **type coercion**.

---

## 7. Truthy and Falsy Values

Falsy values include:

```text
false
0
-0
0n
""
null
undefined
NaN
```

Most other values are truthy.

```js
if ("Hello") {
    console.log("Runs");
}
```

---

## 8. Important Points

* JavaScript is dynamically typed.
* There are 7 primitive data types.
* Objects are non-primitive/reference values.
* Arrays are technically objects.
* `typeof null` returns `"object"` — a historical JavaScript quirk.
* Use `Array.isArray()` to check arrays.
* `NaN` has type `"number"`.
* `const` does not make objects immutable.
* Understand type coercion before using implicit conversions.

---

## Quick Revision

```text
Primitive:
String
Number
BigInt
Boolean
Undefined
Null
Symbol

Non-Primitive:
Object
Array
Function
Date
Map
Set

typeof → checks type
Array.isArray() → checks arrays
```
