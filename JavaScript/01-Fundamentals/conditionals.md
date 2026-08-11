# JavaScript Conditionals

Conditionals allow JavaScript to execute different code depending on a condition.

---

## 1. `if`

Runs code when a condition is `true`.

```js
const age = 20;

if (age >= 18) {
    console.log("Adult");
}
```

---

## 2. `if...else`

Runs one block if true and another if false.

```js
const age = 16;

if (age >= 18) {
    console.log("Adult");
} else {
    console.log("Minor");
}
```

---

## 3. `else if`

Used when there are multiple conditions.

```js
const marks = 75;

if (marks >= 90) {
    console.log("A");
} else if (marks >= 80) {
    console.log("B");
} else if (marks >= 70) {
    console.log("C");
} else {
    console.log("Fail");
}
```

JavaScript checks conditions **from top to bottom** and stops at the first true condition.

---

## 4. Nested `if`

An `if` can exist inside another `if`.

```js
const age = 20;
const hasID = true;

if (age >= 18) {
    if (hasID) {
        console.log("Allowed");
    }
}
```

Avoid excessive nesting when possible.

---

## 5. `switch`

Useful when comparing one value against multiple possible values.

```js
const day = "Monday";

switch (day) {
    case "Monday":
        console.log("Start of week");
        break;

    case "Friday":
        console.log("Weekend soon");
        break;

    default:
        console.log("Normal day");
}
```

### `break`

Stops execution from continuing into the next case.

Without `break`, JavaScript uses **fall-through**.

---

## 6. Ternary Operator

Short form of `if...else`.

```js
const age = 20;

const result = age >= 18 ? "Adult" : "Minor";
```

Syntax:

```js
condition ? valueIfTrue : valueIfFalse;
```

Use it for simple conditions, not complex logic.

---

## 7. Truthy and Falsy

Conditions automatically convert values to Boolean.

Falsy values:

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

Example:

```js
const username = "";

if (username) {
    console.log("Logged in");
} else {
    console.log("No username");
}
```

---

## 8. Logical Operators in Conditions

### AND `&&`

Both conditions must be true.

```js
if (age >= 18 && hasID) {
    console.log("Allowed");
}
```

### OR `||`

At least one condition must be true.

```js
if (isAdmin || isModerator) {
    console.log("Access granted");
}
```

### NOT `!`

Reverses a condition.

```js
if (!isLoggedIn) {
    console.log("Please login");
}
```

---

## 9. Comparison in Conditions

Prefer strict equality:

```js
if (age === 18) {
    console.log("Exactly 18");
}
```

Avoid unnecessary type coercion:

```js
// Prefer
age === 18;

// Instead of
age == 18;
```

---

## Common Mistakes

### Assignment instead of comparison

```js
if (x = 5) {
    // Wrong in most cases
}
```

Use:

```js
if (x === 5) {
    // Correct
}
```

### Forgetting `break` in `switch`

```js
switch (value) {
    case 1:
        console.log("One");
        break;
}
```

### Too many nested conditions

Consider using:

* Early returns
* Functions
* Logical operators
* `switch`

---

## Quick Revision

```text
if
if...else
else if
nested if
switch
ternary ?:
&&
||
!
truthy / falsy
```

**Main idea:**

```text
Condition true  → execute one path
Condition false → execute another path
```
