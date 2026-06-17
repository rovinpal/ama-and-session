# Interview Questions & Answers

## Adhikya Edammala: What are some HTTP methods?

Common HTTP methods:

- **GET** – Retrieve data from a server.
- **POST** – Send new data to a server.
- **PUT** – Update an existing resource completely.
- **PATCH** – Update part of an existing resource.
- **DELETE** – Remove a resource.
- **HEAD** – Retrieve headers only.
- **OPTIONS** – Get supported HTTP methods for a resource.

---

## Allanki VV Manikanta Sai: What is HTTP?

**HTTP (HyperText Transfer Protocol)** is a communication protocol used for transferring data between a client (browser) and a server over the web.

Example:
- Browser requests a webpage using HTTP.
- Server responds with the webpage data.

HTTP is stateless, meaning each request is independent.

---

## Arpit Yadav: Difference between `sorted()` and `.sort()` in Python

| `sorted()` | `.sort()` |
|------------|-----------|
| Returns a new sorted list | Sorts the original list |
| Works with any iterable | Works only with lists |
| Original data remains unchanged | Original data is modified |
| Function | List method |

Example:

```python
nums = [3, 1, 2]

new_nums = sorted(nums)  # [1, 2, 3]
print(nums)              # [3, 1, 2]

nums.sort()
print(nums)              # [1, 2, 3]
```

---

## Boorle Sowmya Sri Lakshmi: Use of `async` and `await` in JavaScript

`async` and `await` simplify handling asynchronous operations.

- `async` makes a function return a Promise.
- `await` pauses execution until a Promise is resolved.

Example:

```javascript
async function getData() {
  const response = await fetch('/api/users');
  const data = await response.json();
  console.log(data);
}
```

Benefits:
- Cleaner syntax
- Easier error handling
- Better readability than `.then()`

---

## Injamuri Arun Kumar: What is an API?

**API (Application Programming Interface)** is a set of rules that allows different software applications to communicate with each other.

Example:
- A weather app requests weather data from a weather service API.
- The API returns the requested data.

Think of an API as a waiter between a customer (client) and a kitchen (server).

---

## Kamparapu Lakshman

*Question not provided.*

---

## M Harivardhan Reddy: How to add a class using DOM?

Use the `classList.add()` method.

Example:

```javascript
const element = document.getElementById("myDiv");
element.classList.add("active");
```

To add multiple classes:

```javascript
element.classList.add("active", "visible");
```

---

## Md Musharaf: What is Client-Server Architecture?

Client-Server Architecture is a model where:

- **Client** sends requests.
- **Server** processes requests and sends responses.

Example:
- Browser → Client
- Web Server → Server

Flow:

```text
Client Request → Server
Client ← Response ← Server
```

---

## Naman Sharma: What is `Promise.allSettled()`?

`Promise.allSettled()` waits for all promises to complete, regardless of whether they succeed or fail.

Example:

```javascript
Promise.allSettled([
  Promise.resolve("Success"),
  Promise.reject("Error")
]).then(results => {
  console.log(results);
});
```

Output:

```javascript
[
  { status: "fulfilled", value: "Success" },
  { status: "rejected", reason: "Error" }
]
```

Unlike `Promise.all()`, it does not fail when one promise rejects.

---

## Nayunipatruni Harsha Vardhan: What is the return type of `fetch()`?

`fetch()` returns a **Promise**.

Specifically:

```javascript
Promise<Response>
```

Example:

```javascript
const result = fetch("/api/users");
console.log(result); // Promise
```

---

## Parlapalli Sulochana: What are Dunder Methods in Python?

Dunder (Double Under) methods are special methods surrounded by double underscores.

Examples:

```python
__init__
__str__
__len__
__add__
```

Example:

```python
class Person:
    def __init__(self, name):
        self.name = name
```

Purpose:
- Customize behavior of objects.
- Enable operator overloading and built-in functionality.

---

## Rongala Vasu: Return type of `null` in JavaScript

```javascript
typeof null
```

Output:

```javascript
"object"
```

This is a well-known historical bug in JavaScript that has been kept for backward compatibility.

---

## Tumma Haritha: Difference between HTTP and HTTPS

| HTTP | HTTPS |
|--------|--------|
| HyperText Transfer Protocol | HyperText Transfer Protocol Secure |
| Data is sent in plain text | Data is encrypted |
| Less secure | More secure |
| Uses port 80 | Uses port 443 |
| No SSL/TLS | Uses SSL/TLS |

Example:

```text
http://example.com
https://example.com
```

---

## Vikas Mehta: Difference between Regular Function and Arrow Function

| Regular Function | Arrow Function |
|------------------|---------------|
| Has its own `this` | Inherits `this` from parent scope |
| Can be used as constructor | Cannot be used as constructor |
| Has `arguments` object | No `arguments` object |
| Function keyword required | Shorter syntax |

Example:

```javascript
function greet() {
  console.log("Hello");
}
```

```javascript
const greet = () => {
  console.log("Hello");
};
```

---

## Yash Nitin Raut: What is Lexical Scoping?

Lexical Scoping means a function can access variables from its outer scope based on where the function is defined.

Example:

```javascript
function outer() {
  let name = "John";

  function inner() {
    console.log(name);
  }

  inner();
}

outer();
```

Output:

```text
John
```

`inner()` can access `name` because it is defined inside `outer()`.

