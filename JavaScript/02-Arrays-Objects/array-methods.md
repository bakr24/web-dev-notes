## 2. map()

Creates a new array by transforming every element.

```js
const numbers = [1, 2, 3];

const doubled = numbers.map(number => number * 2);

console.log(doubled); // [2, 4, 6]

---

## 2. map()

Creates a new array by transforming every element.

```js
const numbers = [1, 2, 3];

const doubled = numbers.map(number => number * 2);

console.log(doubled); // [2, 4, 6]

## 3. filter()

Creates a new array containing elements that match a condition.

```js
const numbers = [1, 2, 3, 4, 5];

const evenNumbers = numbers.filter(number => number % 2 === 0);

console.log(evenNumbers); // [2, 4]
```

Use `filter()` when you want to select multiple elements.

Example:

```js
const users = [
    { name: "Ali", age: 17 },
    { name: "Ahmed", age: 22 },
    { name: "Sara", age: 25 }
];

const adults = users.filter(user => user.age >= 18);

console.log(adults);
// [
//   { name: "Ahmed", age: 22 },
//   { name: "Sara", age: 25 }
// ]
```

## 4. find()

Returns the **first element** that matches a condition.

```js
const numbers = [10, 20, 30, 40];

const result = numbers.find(number => number > 20);

console.log(result); // 30
```

If no element matches, `find()` returns `undefined`.

```js
const numbers = [10, 20, 30];

const result = numbers.find(number => number > 50);

console.log(result); // undefined
```

### `filter()` vs `find()`

```text
filter() → returns all matching elements
find()   → returns the first matching element
```

## 5. findIndex()

Returns the **index of the first element** that matches a condition.

```js
const numbers = [10, 20, 30, 40];

const index = numbers.findIndex(number => number > 20);

console.log(index); // 2
```

If no element matches, `findIndex()` returns `-1`.

```js
const numbers = [10, 20, 30];

const index = numbers.findIndex(number => number > 50);

console.log(index); // -1
```

### `find()` vs `findIndex()`

```text
find()       → returns the element
findIndex()  → returns the element's index
```

## 6. some()

Returns `true` if **at least one element** matches a condition.

```js
const numbers = [1, 3, 4, 7];

const result = numbers.some(number => number % 2 === 0);

console.log(result); // true
```

If no element matches, it returns `false`.

```js
const numbers = [1, 3, 5, 7];

const result = numbers.some(number => number % 2 === 0);

console.log(result); // false
```

### Key Point

```text
some() → Does at least one element match?
```

It always returns a **Boolean**:

```text
true
false
```

## 7. every()

Returns `true` if **all elements** match a condition.

```js
const numbers = [2, 4, 6, 8];

const result = numbers.every(number => number % 2 === 0);

console.log(result); // true
```

If even one element does not match, it returns `false`.

```js
const numbers = [2, 4, 5, 8];

const result = numbers.every(number => number % 2 === 0);

console.log(result); // false
```

### Key Point

```text
every() → Do all elements match?
```

It always returns a **Boolean**:

```text
true
false
```

### some() vs every()

```text
some()  → at least one element matches
every() → all elements match
```

## 8. reduce()

Reduces all elements of an array into **one final value**.

```js
const numbers = [1, 2, 3, 4];

const total = numbers.reduce(
    (sum, number) => sum + number,
    0
);

console.log(total); // 10
```

### How it works

```text
sum = accumulator
number = current element
0 = initial value
```

Step by step:

```text
0 + 1 = 1
1 + 2 = 3
3 + 3 = 6
6 + 4 = 10
```

### Example: Find the total price

```js
const prices = [100, 200, 300];

const total = prices.reduce(
    (sum, price) => sum + price,
    0
);

console.log(total); // 600
```

### Key Point

```text
reduce() → converts an array into one final value
```

Common uses:

- Sum
- Product
- Counting
- Calculating totals
- Grouping data
- Building objects

## 9. sort()

Sorts the elements of an array.

### Numbers — Ascending

```js
const numbers = [10, 2, 30, 5];

numbers.sort((a, b) => a - b);

console.log(numbers); // [2, 5, 10, 30]
```

### Numbers — Descending

```js
const numbers = [10, 2, 30, 5];

numbers.sort((a, b) => b - a);

console.log(numbers); // [30, 10, 5, 2]
```

### Strings

```js
const fruits = ["Mango", "Apple", "Banana"];

fruits.sort();

console.log(fruits);
// ["Apple", "Banana", "Mango"]
```

### Important

`sort()` modifies the **original array**.

```text
sort() → sorts the array
a - b  → ascending
b - a  → descending
```

## 10. reverse()

Reverses the order of elements in an array.

```js
const numbers = [1, 2, 3, 4];

numbers.reverse();

console.log(numbers); // [4, 3, 2, 1]
```

### Example

```js
const fruits = ["Apple", "Banana", "Mango"];

fruits.reverse();

console.log(fruits);
// ["Mango", "Banana", "Apple"]
```

### Important

`reverse()` modifies the **original array**.

```text
reverse() → reverses the array
```