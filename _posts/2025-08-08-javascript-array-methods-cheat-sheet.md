---
title: "JavaScript Array Methods Cheat Sheet"
date: 2025-08-08 12:00:00 -0500
categories: [Programming, JavaScript]
tags: [javascript, arrays, cheatsheet, methods]
pin: true
---

# JavaScript Array Methods: A Comprehensive Guide

Working with arrays is fundamental in JavaScript. Here's a comprehensive guide to the most useful array methods with practical examples.

## Mutation Methods (Modify Original Array)

### `push()` and `pop()`

```javascript
const fruits = ['apple', 'banana'];

// Add to end
fruits.push('orange'); // ['apple', 'banana', 'orange']

// Remove from end
const lastFruit = fruits.pop(); // 'orange'
console.log(fruits); // ['apple', 'banana']
```

### `unshift()` and `shift()`

```javascript
const numbers = [2, 3, 4];

// Add to beginning
numbers.unshift(1); // [1, 2, 3, 4]

// Remove from beginning
const firstNumber = numbers.shift(); // 1
console.log(numbers); // [2, 3, 4]
```

### `splice()`

```javascript
const colors = ['red', 'green', 'blue', 'yellow'];

// Remove 2 elements starting at index 1, add 'purple'
colors.splice(1, 2, 'purple'); 
console.log(colors); // ['red', 'purple', 'yellow']
```

## Non-Mutation Methods (Return New Array)

### `map()`

Transform each element:

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8]

// With objects
const users = [
  { name: 'John', age: 25 },
  { name: 'Jane', age: 30 }
];

const names = users.map(user => user.name);
console.log(names); // ['John', 'Jane']
```

### `filter()`

Select elements that meet criteria:

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4, 6]

// Filter objects
const adults = users.filter(user => user.age >= 18);
```

### `reduce()`

Accumulate values:

```javascript
const numbers = [1, 2, 3, 4];

// Sum all numbers
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
console.log(sum); // 10

// Group by property
const people = [
  { name: 'John', department: 'IT' },
  { name: 'Jane', department: 'HR' },
  { name: 'Bob', department: 'IT' }
];

const groupedByDept = people.reduce((acc, person) => {
  if (!acc[person.department]) {
    acc[person.department] = [];
  }
  acc[person.department].push(person);
  return acc;
}, {});
```

## Search Methods

### `find()` and `findIndex()`

```javascript
const products = [
  { id: 1, name: 'Laptop', price: 1000 },
  { id: 2, name: 'Phone', price: 500 },
  { id: 3, name: 'Tablet', price: 300 }
];

// Find first match
const laptop = products.find(product => product.name === 'Laptop');

// Find index
const phoneIndex = products.findIndex(product => product.name === 'Phone');
console.log(phoneIndex); // 1
```

### `includes()` and `indexOf()`

```javascript
const fruits = ['apple', 'banana', 'orange'];

console.log(fruits.includes('banana')); // true
console.log(fruits.indexOf('orange')); // 2
console.log(fruits.indexOf('grape')); // -1 (not found)
```

## Testing Methods

### `some()` and `every()`

```javascript
const numbers = [1, 2, 3, 4, 5];

// Check if any element meets criteria
const hasEven = numbers.some(num => num % 2 === 0);
console.log(hasEven); // true

// Check if all elements meet criteria
const allPositive = numbers.every(num => num > 0);
console.log(allPositive); // true
```

## Utility Methods

### `sort()`

```javascript
const numbers = [3, 1, 4, 1, 5];

// Numeric sort
numbers.sort((a, b) => a - b); // [1, 1, 3, 4, 5]

// String sort (case-insensitive)
const names = ['John', 'jane', 'Bob'];
names.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase()));
```

### `join()` and `slice()`

```javascript
const words = ['Hello', 'World', 'JavaScript'];

// Join with separator
const sentence = words.join(' '); // "Hello World JavaScript"

// Extract portion
const firstTwo = words.slice(0, 2); // ['Hello', 'World']
```

## Method Chaining

Combine methods for powerful data transformations:

```javascript
const sales = [
  { product: 'Laptop', amount: 1000, month: 'Jan' },
  { product: 'Phone', amount: 500, month: 'Jan' },
  { product: 'Laptop', amount: 1200, month: 'Feb' },
  { product: 'Tablet', amount: 300, month: 'Feb' }
];

const totalLaptopSales = sales
  .filter(sale => sale.product === 'Laptop')
  .map(sale => sale.amount)
  .reduce((total, amount) => total + amount, 0);

console.log(totalLaptopSales); // 2200
```

## Performance Tips

1. **Use `for` loops** for simple iterations when performance is critical
2. **`some()` and `every()`** stop at first match/mismatch
3. **`find()`** stops at first match (better than `filter()[0]`)
4. **Avoid chaining** too many methods on large arrays

## Common Patterns

### Remove duplicates

```javascript
const numbers = [1, 2, 2, 3, 3, 4];
const unique = [...new Set(numbers)]; // [1, 2, 3, 4]

// For objects (by property)
const uniqueById = data.filter((item, index, self) => 
  index === self.findIndex(obj => obj.id === item.id)
);
```

### Flatten arrays

```javascript
const nested = [[1, 2], [3, 4], [5]];
const flattened = nested.flat(); // [1, 2, 3, 4, 5]

// Deep flatten
const deepNested = [1, [2, [3, [4]]]];
const deepFlattened = deepNested.flat(Infinity); // [1, 2, 3, 4]
```

Array methods are incredibly powerful tools in JavaScript. Master these patterns and you'll write more readable, functional code!

---

*Which array method do you find most useful? Any clever patterns you'd like to share?*
