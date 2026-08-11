# JavaScript Loops

Loops repeat a block of code while a condition is true or for each item in a collection.

---

## 1. `for` Loop

Used when you know how many times you want to repeat something.

```js
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

Output:

```text
0
1
2
3
4
```

Structure:

```js
for (initialization; condition; update) {
    // code
}
```

---

## 2. `while` Loop

Runs while a condition is true.

```js
let i = 0;

while (i < 5) {
    console.log(i);
    i++;
}
```

Make sure the condition eventually becomes false, otherwise you get an **infinite loop**.

---

## 3. `do...while`

Runs the code **at least once**, even if the condition is false.

```js
let i = 10;

do {
    console.log(i);
    i++;
} while (i < 5);
```

Output:

```text
10
```

---

## 4. `for...of`

Used to iterate over values in iterables such as arrays and strings.

```js
const fruits = ["Apple", "Banana", "Mango"];

for (const fruit of fruits) {
    console.log(fruit);
}
```

Output:

```text
Apple
Banana
Mango
```

Also works with strings:

```js
for (const char of "Hello") {
    console.log(char);
}
```

---

## 5. `for...in`

Used to iterate over the **keys/properties** of an object.

```js
const user = {
    name: "Abubakar",
    age: 22
};

for (const key in user) {
    console.log(key);
}
```

Output:

```text
name
age
```

To get the value:

```js
for (const key in user) {
    console.log(user[key]);
}
```

### Important

Prefer `for...of` for arrays.

```js
// Good for arrays
for (const item of items) {}
```

`for...in` is primarily for object properties.

---

## 6. `break`

Immediately stops the loop.

```js
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

Output:

```text
0
1
2
3
4
```

---

## 7. `continue`

Skips the current iteration and continues with the next one.

```js
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;
    }

    console.log(i);
}
```

Output:

```text
0
1
3
4
```

---

## 8. Nested Loops

A loop can contain another loop.

```js
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 2; j++) {
        console.log(i, j);
    }
}
```

Useful for:

* 2D arrays
* Grids
* Tables
* Matrix problems

---

## 9. Infinite Loops

A loop that never becomes false.

```js
while (true) {
    console.log("Forever");
}
```

Avoid infinite loops unless intentionally using them with a `break`.

---

## 10. Looping Through Arrays

Traditional:

```js
const numbers = [10, 20, 30];

for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}
```

Modern:

```js
for (const number of numbers) {
    console.log(number);
}
```

For transformations and filtering, array methods are often better:

```js
numbers.map(...)
numbers.filter(...)
numbers.forEach(...)
```

---

## Common Mistakes

### Forgetting to update the counter

```js
let i = 0;

while (i < 5) {
    console.log(i);
}
```

This creates an infinite loop.

### Wrong boundary

```js
for (let i = 0; i <= arr.length; i++) {
    console.log(arr[i]);
}
```

Usually use:

```js
i < arr.length
```

because the last valid index is `length - 1`.

### Using `for...in` for arrays

Prefer:

```js
for (const item of array) {}
```

---

## Quick Revision

```text
for          → known/repeated iterations
while        → repeat while condition is true
do...while   → runs at least once
for...of     → values
for...in     → object keys
break        → stop loop
continue     → skip iteration
nested loop  → loop inside loop
```

### Rule to Remember

```text
Array → for...of
Object → for...in
```
