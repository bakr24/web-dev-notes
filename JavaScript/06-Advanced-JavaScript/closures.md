# JavaScript Closures

A **closure** is created when a function remembers and can access variables from its outer scope, even after the outer function has finished executing.

---

## 1. Basic Example

```js
function outer() {
    const message = "Hello";

    function inner() {
        console.log(message);
    }

    return inner;
}

const greet = outer();

greet(); // Hello
```

`inner()` remembers `message` even though `outer()` has already finished.

---

## 2. How Closures Work

A closure consists of:

```text
Function
   +
Its surrounding lexical environment
```

The inner function keeps access to variables from its outer scope.

---

## 3. Closures with Parameters

```js
function createGreeting(name) {
    return function () {
        console.log(`Hello ${name}`);
    };
}

const greet = createGreeting("Abubakar");

greet(); // Hello Abubakar
```

The returned function remembers `name`.

---

## 4. Data Privacy

Closures can keep variables private.

```js
function createCounter() {
    let count = 0;

    return {
        increment() {
            count++;
        },

        getCount() {
            return count;
        }
    };
}

const counter = createCounter();

counter.increment();
counter.increment();

console.log(counter.getCount()); // 2
```

`count` cannot be accessed directly:

```js
// counter.count → undefined
```

---

## 5. Multiple Closures

Each function call creates a separate closure.

```js
function createCounter() {
    let count = 0;

    return () => ++count;
}

const counter1 = createCounter();
const counter2 = createCounter();

console.log(counter1()); // 1
console.log(counter1()); // 2

console.log(counter2()); // 1
```

`counter1` and `counter2` have separate `count` variables.

---

## 6. Closures in Loops

A common issue occurs with `var`.

```js
for (var i = 0; i < 3; i++) {
    setTimeout(() => {
        console.log(i);
    }, 100);
}
```

Output:

```text
3
3
3
```

`var` has function scope, so all callbacks share the same `i`.

Using `let` creates a new binding for each iteration:

```js
for (let i = 0; i < 3; i++) {
    setTimeout(() => {
        console.log(i);
    }, 100);
}
```

Output:

```text
0
1
2
```

---

## 7. Closures and Callbacks

Closures are commonly used with callbacks.

```js
function delayedGreeting(name) {
    setTimeout(() => {
        console.log(`Hello ${name}`);
    }, 1000);
}

delayedGreeting("Abubakar");
```

The callback remembers `name`.

---

## 8. Closures and `setTimeout`

```js
function timer() {
    const message = "Done";

    setTimeout(() => {
        console.log(message);
    }, 1000);
}

timer();
```

Even after `timer()` finishes, the callback can still access `message`.

---

## 9. Closures in JavaScript Applications

Closures are commonly used for:

* Data privacy
* Counters
* Factory functions
* Callbacks
* Event handlers
* Memoization
* Function factories
* Maintaining state

They are also important for understanding **React hooks and state behavior**.

---

## 10. Memory Consideration

A closure keeps references to variables it needs.

Therefore, unnecessary closures that retain large objects can contribute to memory usage.

Good practice:

* Don't unnecessarily retain large objects.
* Remove event listeners when appropriate.
* Avoid creating unnecessary long-lived closures.

---

## Common Mistakes

### Thinking the outer function must remain running

It doesn't.

```js
function outer() {
    const x = 10;

    return () => x;
}

const fn = outer();

console.log(fn()); // 10
```

`outer()` has finished, but the closure still has access to `x`.

### Confusing closure with scope

**Scope** determines where variables are accessible.

**Closure** allows a function to retain access to its surrounding lexical environment.

---

## Quick Revision

```text
Closure =
Function + surrounding lexical environment

Used for:
→ Data privacy
→ Callbacks
→ State
→ Factory functions
→ Memoization
→ Event handlers

Key idea:

Outer function runs
       ↓
Inner function remembers variables
       ↓
Outer function finishes
       ↓
Inner function still accesses them
```
