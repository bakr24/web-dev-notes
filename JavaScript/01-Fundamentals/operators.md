# JavaScript Operators

Operators are symbols used to perform operations on values and variables.

```js
const a = 10;
const b = 5;

console.log(a + b); // 15
```

---

## 1. Arithmetic Operators

Used for mathematical operations.

| Operator | Meaning        | Example         |
| -------- | -------------- | --------------- |
| `+`      | Addition       | `10 + 5` → `15` |
| `-`      | Subtraction    | `10 - 5` → `5`  |
| `*`      | Multiplication | `10 * 5` → `50` |
| `/`      | Division       | `10 / 5` → `2`  |
| `%`      | Remainder      | `10 % 3` → `1`  |
| `**`     | Exponent       | `2 ** 3` → `8`  |

---

## 2. Assignment Operators

Used to assign or update values.

```js
let x = 10;

x += 5;  // 15
x -= 2;  // 13
x *= 2;  // 26
x /= 2;  // 13
x %= 5;  // 3
```

Common operators:

```text
=   +=   -=   *=   /=   %=   **=
```

---

## 3. Comparison Operators

Used to compare values. They return `true` or `false`.

```js
10 > 5;    // true
10 < 5;    // false
10 >= 10;  // true
10 <= 5;   // false
```

Operators:

```text
>    Greater than
<    Less than
>=   Greater than or equal
<=   Less than or equal
```

---

## 4. Equality Operators

### Loose Equality `==`

Compares values after type conversion.

```js
5 == "5"; // true
```

### Strict Equality `===`

Compares both value **and type**.

```js
5 === "5"; // false
5 === 5;   // true
```

### Not Equal

```js
5 != "5";   // false
5 !== "5";  // true
```

### Best Practice

Prefer:

```js
===
!==
```

over:

```js
==
!=
```

because strict equality avoids unexpected type coercion.

---

## 5. Logical Operators

Used to combine conditions.

### AND `&&`

Returns true when both conditions are true.

```js
true && true;   // true
true && false;  // false
```

Example:

```js
const age = 22;

age >= 18 && age <= 30;
```

### OR `||`

Returns true when at least one condition is true.

```js
true || false; // true
false || false; // false
```

### NOT `!`

Reverses a Boolean value.

```js
!true;  // false
!false; // true
```

---

## 6. Increment and Decrement

### Increment `++`

```js
let count = 5;

count++;

console.log(count); // 6
```

### Decrement `--`

```js
let count = 5;

count--;

console.log(count); // 4
```

---

## 7. Ternary Operator

Short form of an `if...else`.

Syntax:

```js
condition ? valueIfTrue : valueIfFalse;
```

Example:

```js
const age = 20;

const result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

Output:

```text
Adult
```

---

## 8. Nullish Coalescing `??`

Returns the right-hand value only when the left side is `null` or `undefined`.

```js
const username = null;

const name = username ?? "Guest";

console.log(name); // Guest
```

Important:

```js
0 ?? 10;       // 0
"" ?? "Hello"; // ""
false ?? true; // false
```

Unlike `||`, `??` does not treat `0`, `""`, or `false` as missing.

---

## 9. Optional Chaining `?.`

Safely accesses nested properties.

```js
const user = {
    profile: {
        name: "Abubakar"
    }
};

console.log(user.profile?.name);
```

If `profile` doesn't exist:

```js
const user = {};

console.log(user.profile?.name);
```

Instead of throwing an error, it returns:

```text
undefined
```

---

## 10. `typeof` Operator

Checks the type of a value.

```js
typeof "Hello"; // "string"
typeof 10;      // "number"
typeof true;    // "boolean"
```

---

## 11. Operator Precedence

Some operators are evaluated before others.

```js
const result = 2 + 3 * 4;
```

Multiplication happens first:

```text
2 + 12 = 14
```

Use parentheses when you want to make the order explicit:

```js
const result = (2 + 3) * 4;
// 20
```

---

## Quick Revision

```text
Arithmetic:
+  -  *  /  %  **

Assignment:
=  +=  -=  *=  /=  %=

Comparison:
>  <  >=  <=

Equality:
==  !=
=== !==

Logical:
&&  ||  !

Increment:
++  --

Decrement:
--

Ternary:
condition ? trueValue : falseValue

Nullish:
??

Optional chaining:
?.

Type:
typeof
```

### Best Practices

* Prefer `===` and `!==`.
* Use parentheses when expressions become complex.
* Use `??` when you specifically want to handle `null`/`undefined`.
* Use `?.` when accessing potentially missing nested properties.
* Don't overuse complex one-line ternary expressions.
