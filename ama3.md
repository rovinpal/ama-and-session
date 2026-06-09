# AMA SESSION QUESTIONS AND ANSWERS:

## Adhikya Edammala: What is a debugger?

A **debugger** is a tool used to find and fix errors (bugs) in a program. It allows developers to:

- Pause code execution (breakpoints)
- Inspect variables and their values
- Execute code line by line
- Analyze the call stack

In JavaScript, you can use the `debugger` statement:

```
let x = 10;
debugger; // Execution pauses here if DevTools is open
console.log(x);
```

---

## Allanki VV Manikanta Sai: Some non-primitive data types

Non-primitive (reference) data types in JavaScript include:

- `Object`
- `Array`
- `Function`
- `Date`
- `Map`
- `Set`
- `RegExp`

Example:

```
const person = {
  name: "John",
  age: 25
};
```

Unlike primitive types, non-primitives are stored and passed by reference.

---

## Arpit Yadav: How do we remove an event listener from an element?

Use the `removeEventListener()` method.

```
function handleClick() {
  console.log("Clicked");
}

button.addEventListener("click", handleClick);

// Remove listener
button.removeEventListener("click", handleClick);
```

**Note:** The same function reference must be provided to remove the listener.

---

## Boorle Sowmya Sri Lakshmi: What are polyfills in JavaScript?

A **polyfill** is code that provides modern JavaScript functionality in older browsers that do not support it.

Example:

```
if (!Array.prototype.includes) {
  Array.prototype.includes = function(value) {
    return this.indexOf(value) !== -1;
  };
}
```

Polyfills help maintain compatibility across different browser versions.

---

## Injamuri Arun Kumar: What is the return type of `null`?

```
typeof null;
```

Output:

```
"object"
```

This is a well-known historical bug in JavaScript. Although `null` represents the intentional absence of a value, `typeof null` returns `"object"`.

---

## Kamparapu Lakshman: What do `some()` and `every()` methods do in an array?

### `some()`
Returns `true` if **at least one** element satisfies the condition.

```
const nums = [1, 2, 3, 4];

nums.some(num => num > 3); // true
```

### `every()`
Returns `true` only if **all** elements satisfy the condition.

```
const nums = [1, 2, 3, 4];

nums.every(num => num > 0); // true
```

---

## M Harivardhan Reddy: What is a callback function?

A **callback function** is a function passed as an argument to another function and executed later.

```
function greet(name, callback) {
  console.log("Hello " + name);
  callback();
}

greet("John", function() {
  console.log("Welcome!");
});
```

Callbacks are commonly used in asynchronous operations.

---

## Md Musharaf: What is the rest operator in JavaScript?

The **rest operator (`...`)** collects multiple values into a single array.

```
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}

sum(1, 2, 3, 4); // 10
```

It is useful when the number of arguments is unknown.

---

## Naman Sharma: Difference between `call()` and `apply()`

Both methods invoke a function with a specified `this` value.

### `call()`
Arguments are passed individually.

```
person.greet.call(user, "Hello", "!");
```

### `apply()`
Arguments are passed as an array.

```
person.greet.apply(user, ["Hello", "!"]);
```

### Example

```
function greet(msg) {
  console.log(msg + " " + this.name);
}

const user = { name: "John" };

greet.call(user, "Hello");
greet.apply(user, ["Hi"]);
```

---

## Nayunipatruni Harsha Vardhan: Difference between `filter()` and `find()`

### `filter()`
Returns **all matching elements** as a new array.

```
const nums = [1, 2, 3, 4];

nums.filter(num => num > 2);
// [3, 4]
```

### `find()`
Returns **only the first matching element**.

```
const nums = [1, 2, 3, 4];

nums.find(num => num > 2);
// 3
```

---

## Parlapalli Sulochana: How do we create custom errors?

Create a class that extends the built-in `Error` class.

```
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

throw new ValidationError("Invalid input");
```

Benefits:
- Better error categorization
- Easier debugging
- Cleaner error handling

---

## Rongala Vasu: Difference between dot notation and bracket notation

### Dot Notation

```
const user = {
  name: "John"
};

console.log(user.name);
```

### Bracket Notation

```
console.log(user["name"]);
```

### When to use bracket notation?

1. Dynamic property names:

```
const key = "name";
console.log(user[key]);
```

2. Property names containing spaces or special characters:

```
const obj = {
  "first name": "John"
};

console.log(obj["first name"]);
```

---

## Tumma Haritha: What does `preventDefault()` do?

The `preventDefault()` method prevents the browser's default behavior for an event.

Example:

```
document.querySelector("a").addEventListener("click", function(event) {
  event.preventDefault();
});
```

Common uses:
- Prevent form submission
- Prevent link navigation
- Prevent context menu actions

---

## Vikas Mehta: What do you mean by method chaining?

**Method chaining** is calling multiple methods on the same object in a single statement.

```
const result = [1, 2, 3, 4]
  .filter(num => num > 2)
  .map(num => num * 2)
  .join(", ");

console.log(result); // "6, 8"
```

Benefits:
- Cleaner code
- Improved readability
- Reduced temporary variables

---

## Yash Nitin Raut: Is JavaScript interpreted or compiled?

Modern JavaScript is **both interpreted and compiled**.

1. JavaScript code is parsed.
2. Engines like **V8** use **Just-In-Time (JIT) compilation**.
3. Frequently executed code is compiled into machine code for better performance.

So, JavaScript is commonly described as a **JIT-compiled language**, combining features of both interpretation and compilation.
