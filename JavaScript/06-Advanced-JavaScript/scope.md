# JavaScript Scope

Scope determines **where a variable can be accessed** in your code.

---

## 1. Global Scope

A variable declared outside functions or blocks is globally accessible.

```js
const name = "Abubakar";

function greet() {
    console.log(name);
}

greet();
```

`name` can be accessed inside the function because it exists in the outer scope.

---

## 2. Function Scope

Variables declared with `var` inside a function are available throughout that function.

```js
function test() {
    var message = "Hello";

    console.log(message);
}

test();

// console.log(message); // Error
```

---

## 3. Block Scope

`let` and `const` are block-scoped.

A block is usually defined by `{ }`.

```js
if (true) {
    let age = 22;
    const name = "Abubakar";

    console.log(age);
}

// console.log(age); // Error
```

---

## 4. `var` vs `let` / `const`

`var` is **not block-scoped**.

```js
if (true) {
    var x = 10;
}

console.log(x); // 10
```

But `let` and `const` are:

```js
if (true) {
    let y = 20;
}

// console.log(y); // Error
```

### Best Practice

Prefer:

```js
let
const
```

Avoid using `var` in modern JavaScript unless you specifically need its behavior.

---

## 5. Lexical Scope

A function can access variables from the scope where the function was **defined**.

```js
const name = "Abubakar";

function greet() {
    console.log(name);
}

greet();
```

JavaScript determines scope based on where code is written, not where a function is called.

---

## 6. Scope Chain

When JavaScript looks for a variable, it searches:

```text
Current scope
     ↓
Outer scope
     ↓
Global scope
```

Example:

```js
const a = 10;

function outer() {
    const b = 20;

    function inner() {
        const c = 30;

        console.log(a);
        console.log(b);
        console.log(c);
    }

    inner();
}
```

`inner()` can access variables from its own scope and outer scopes.

---

## 7. Variable Shadowing

An inner scope can declare a variable with the same name as an outer variable.

```js
const name = "Abubakar";

function test() {
    const name = "Ali";

    console.log(name); // Ali
}

test();

console.log(name); // Abubakar
```

The inner variable **shadows** the outer variable.

---

## 8. Scope and `const`

`const` prevents reassignment, but scope still applies.

```js
const user = {
    name: "Abubakar"
};

user.name = "Ali"; // Allowed
```

`const` means the variable cannot point to a different value; it does not make an object immutable.

---

## 9. Temporal Dead Zone

`let` and `const` are hoisted but cannot be accessed before their declaration.

```js
console.log(name); // ReferenceError

let name = "Abubakar";
```

The period between entering the scope and reaching the declaration is called the **Temporal Dead Zone (TDZ)**.

---

## 10. Scope vs Hoisting

These are different concepts.

**Scope** answers:

> Where can I access this variable?

**Hoisting** answers:

> How does JavaScript handle declarations before execution?

Example:

```js
function test() {
    console.log(x);

    var x = 10;
}
```

With `var`, the declaration is hoisted:

```js
function test() {
    var x;

    console.log(x); // undefined

    x = 10;
}
```

---

## Common Mistakes

### Accessing block variables outside

```js
if (true) {
    let x = 10;
}

// console.log(x); // Error
```

### Assuming `const` makes objects immutable

```js
const user = { name: "Ali" };

user.name = "Ahmed"; // Allowed
```

### Using variables before `let` / `const` initialization

```js
console.log(x); // ReferenceError

const x = 10;
```

---

## Quick Revision

```text
Global Scope       → accessible globally
Function Scope     → accessible inside function
Block Scope        → let/const inside {}
Lexical Scope      → scope based on where code is written
Scope Chain        → current → outer → global
Shadowing          → inner variable hides outer variable
TDZ                → let/const before initialization
```

### Main Rule

```text
Inner scopes can access outer variables,
but outer scopes cannot access inner variables.
```
