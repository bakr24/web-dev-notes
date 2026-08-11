# JavaScript Arrays

An **array** stores multiple values in a single variable.

## 1. Creating an Array

```js
const fruits = ["Apple", "Banana", "Mango"];
```

Access values using an index:

```js
console.log(fruits[0]); // Apple
console.log(fruits[2]); // Mango
```

Indexes start at **0**.

---

## 2. Changing Values

Arrays are mutable.

```js
const fruits = ["Apple", "Banana"];

fruits[1] = "Mango";

console.log(fruits);
```

---

## 3. Array Length

```js
const numbers = [10, 20, 30];

console.log(numbers.length); // 3
```

Last element:

```js
numbers[numbers.length - 1];
```

---

## 4. Adding and Removing

### `push()`

Adds to the end.

```js
numbers.push(40);
```

### `pop()`

Removes from the end.

```js
numbers.pop();
```

### `unshift()`

Adds to the beginning.

```js
numbers.unshift(5);
```

### `shift()`

Removes from the beginning.

```js
numbers.shift();
```

---

## 5. `slice()`

Returns a portion of an array without modifying the original.

```js
const numbers = [1, 2, 3, 4, 5];

const result = numbers.slice(1, 4);

console.log(result); // [2, 3, 4]
```

The ending index is not included.

---

## 6. `splice()`

Adds/removes elements and **modifies the original array**.

```js
const numbers = [1, 2, 3, 4];

numbers.splice(1, 2);

console.log(numbers); // [1, 4]
```

---

## 7. Checking Elements

### `includes()`

```js
const fruits = ["Apple", "Banana"];

fruits.includes("Apple"); // true
```

### `indexOf()`

```js
fruits.indexOf("Banana"); // 1
```

Returns `-1` if not found.

---

## 8. Looping Through Arrays

```js
const numbers = [10, 20, 30];

for (const number of numbers) {
    console.log(number);
}
```

You can also use:

```js
numbers.forEach(number => {
    console.log(number);
});
```

---

## 9. Nested Arrays

Arrays can contain other arrays.

```js
const matrix = [
    [1, 2],
    [3, 4]
];

console.log(matrix[0][1]); // 2
```

Useful for grids and matrices.

---

## 10. Spread Operator

Create a new array from another array:

```js
const numbers = [1, 2, 3];

const copy = [...numbers];
```

Combine arrays:

```js
const a = [1, 2];
const b = [3, 4];

const combined = [...a, ...b];
```

---

## 11. Destructuring

Extract values into variables.

```js
const fruits = ["Apple", "Banana", "Mango"];

const [first, second] = fruits;

console.log(first);  // Apple
console.log(second); // Banana
```

---

## 12. Important Array Methods

These will be covered in detail in `array-methods.md`:

```text
forEach() → execute for each item
map()     → create a new transformed array
filter()  → create array with matching items
find()    → find first matching item
some()    → at least one matches
every()   → all match
reduce()  → combine values into one result
sort()    → sort elements
```

---

## Common Mistakes

### Index starts at 0

```js
const fruits = ["Apple", "Banana"];

fruits[0]; // Apple
fruits[1]; // Banana
```

### `slice()` vs `splice()`

```text
slice()  → doesn't modify original
splice() → modifies original
```

---

## Quick Revision

```text
Array
 ↓
[index]
 ↓
0, 1, 2, 3...

push()     → add end
pop()      → remove end
unshift()  → add beginning
shift()    → remove beginning
slice()    → copy portion
splice()   → modify array
includes() → check value
indexOf()  → find index
```
