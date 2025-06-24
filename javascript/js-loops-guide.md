
# 🔁 Mastering Loops in JavaScript — Using a Products Array for Practical Examples

Loops are fundamental in programming. They help you process data collections, automate repetitive tasks, and build dynamic apps.

In this post, we’ll learn how to use different types of loops in JavaScript with a **products array** as our working example.

---

## 📦 Our Products Array

```js
const products = [
  { id: 1, name: 'Laptop', price: 1200, inStock: true },
  { id: 2, name: 'Smartphone', price: 800, inStock: false },
  { id: 3, name: 'Tablet', price: 400, inStock: true },
  { id: 4, name: 'Monitor', price: 300, inStock: true },
];
```

---

## 1. The Classic `for` Loop (Index-Based)

The classic `for` loop is great when you need to access array elements via their index, control iteration explicitly, or need to break/continue based on conditions.

```js
for (let i = 0; i < products.length; i++) {
  if (products[i].inStock) {
    console.log(`(for loop) ${products[i].name} is available at $${products[i].price}`);
  }
}
```

---

## 2. The `while` Loop

```js
let index = 0;
while (index < products.length) {
  const product = products[index];
  if (product.inStock) {
    console.log(`(while loop) ${product.name} is available at $${product.price}`);
  }
  index++;
}
```

---

## 3. The `do...while` Loop

```js
let idx = 0;
do {
  const product = products[idx];
  if (product.inStock) {
    console.log(`(do...while loop) ${product.name} is available at $${product.price}`);
  }
  idx++;
} while (idx < products.length);
```

---

## 4. The Modern `for...of` Loop (Value-Based)

```js
for (const product of products) {
  if (product.inStock) {
    console.log(`(for...of) ${product.name} is available at $${product.price}`);
  }
}
```

---

## 5. Using `forEach` for Side Effects

```js
products.forEach(product => {
  if (product.inStock) {
    console.log(`(forEach) ${product.name} is available at $${product.price}`);
  }
});
```

---

## 6. Using `filter` to Select, then `forEach` to Act

```js
const availableProducts = products.filter(product => product.inStock);

availableProducts.forEach(product => {
  console.log(`(filter + forEach) ${product.name} at $${product.price}`);
});
```

---

## 7. Using `map` to Transform Data

```js
const productNames = products.map(product => product.name);
console.log('(map) Product Names:', productNames);
```

---

## 8. When to Use Which Loop?

| Scenario                                  | Recommended Loop/Method          | Notes                                         |
|-------------------------------------------|----------------------------------|-----------------------------------------------|
| Need index or break/continue control      | Classic `for`                   | Most flexible                                 |
| Loop until a condition is met             | `while` / `do...while`          | Good for unknown iteration count              |
| Loop over values, no index needed         | `for...of`                      | Clean and readable                            |
| Run a function on all array items         | `forEach`                       | No early exit possible                         |
| Filter and then act on filtered results   | `filter` + `forEach`            | Clear separation of concerns                   |
| Transform array into a new array          | `map`                           | Creates new array without mutating original   |

---

## Final Thoughts

- Use **classic `for`** when you need indexes or control.
- Use **`while`/`do...while`** when looping until a dynamic condition.
- Use **`for...of`** for clean iteration over values.
- Use **functional methods** (`filter`, `map`, `reduce`) when you want declarative and immutable data transformations.

---

## Try It Yourself!

```js
// Task: List all products priced over $500
const expensiveProducts = products.filter(p => p.price > 500);
expensiveProducts.forEach(p => console.log(p.name + " is expensive"));
```
