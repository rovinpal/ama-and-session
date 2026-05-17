# Python Dictionary Operations & Methods

## What is a Dictionary?

A **dictionary** in Python is a mutable, unordered collection of key-value pairs.

```
student = {
    "name": "John",
    "age": 24,
    "course": "Python"
}
```

- Keys must be unique
- Keys must be immutable (`str`, `int`, `tuple`)
- Values can be any datatype

---

# 1. Creating Dictionaries

## Empty Dictionary

```
d = {}
# or
d = dict()
```

## With Values

```
person = {
    "name": "Alice",
    "age": 25
}
```

## Using `dict()`

```
user = dict(name="Bob", age=30)
```

---

# 2. Accessing Values

## Using Keys

```
student["name"]
```

Raises `KeyError` if key does not exist.

## Using `get()`

```
student.get("name")
student.get("marks", 0)
```

- Safe access
- Returns default value if key not found

---

# 3. Adding & Updating Values

## Add New Key

```
student["city"] = "Udupi"
```

## Update Existing Key

```
student["name"] = "Rovin"
```

## Using `update()`

```
student.update({
    "age": 23,
    "course": "Python-Django"
})
```

---

# 4. Removing Items

## `pop()`

Removes a key and returns its value.

```
student.pop("age")
```

Default value prevents errors:

```
student.pop("marks", 0)
```

---

## `popitem()`

Removes the last inserted item.

```
student.popitem()
```

---

## `del`

```
del student["course"]
```

Delete entire dictionary:

```
del student
```

---

## `clear()`

Removes all items.

```
student.clear()
```

---

# 5. Dictionary Length

```
len(student)
```

---

# 6. Checking Keys

## `in` Operator

```
"name" in student
```

## `not in`

```
"marks" not in student
```

---

# 7. Dictionary Traversal

## Loop Through Keys

```
for key in student:
    print(key)
```

---

## Loop Through Values

```
for value in student.values():
    print(value)
```

---

## Loop Through Key-Value Pairs

```
for key, value in student.items():
    print(key, value)
```

---

# 8. Important Dictionary Methods

| Method | Description |
|---|---|
| `get()` | Returns value safely |
| `keys()` | Returns all keys |
| `values()` | Returns all values |
| `items()` | Returns key-value pairs |
| `update()` | Updates dictionary |
| `pop()` | Removes specific key |
| `popitem()` | Removes last item |
| `clear()` | Removes all items |
| `copy()` | Creates shallow copy |
| `setdefault()` | Returns value; inserts if absent |
| `fromkeys()` | Creates dictionary from keys |

---

# 9. Copying Dictionaries

## Shallow Copy

```
copy_dict = student.copy()
```

Or:

```
copy_dict = dict(student)
```

---

# 10. `setdefault()`

Returns value if key exists.

If not, inserts key with default value.

```
student.setdefault("marks", 0)
```

---

# 11. `fromkeys()`

Creates dictionary using keys.

```
keys = ["a", "b", "c"]

d = dict.fromkeys(keys, 0)

print(d)
```

Output:

```
{'a': 0, 'b': 0, 'c': 0}
```

---

# 12. Nested Dictionaries

```
students = {
    "s1": {
        "name": "John",
        "age": 20
    },
    "s2": {
        "name": "Alice",
        "age": 22
    }
}
```

Access:

```
students["s1"]["name"]
```

---

# 13. Dictionary Comprehension

## Basic Example

```
squares = {x: x*x for x in range(5)}
```

Output:

```
{0:0, 1:1, 2:4, 3:9, 4:16}
```

---

## With Condition

```
even = {x: x*x for x in range(10) if x % 2 == 0}
```

---

# 14. Merging Dictionaries

## Using `update()`

```
d1.update(d2)
```

---

## Using `|` Operator (Python 3.9+)

```
merged = d1 | d2
```

---

# 15. Sorting Dictionaries

## Sort by Keys

```
sorted(student.keys())
```

## Sort by Values

```
sorted(student.values())
```

---

## Sort Key-Value Pairs

```
sorted(student.items())
```

---

# 16. Common Dictionary Operations

## Count Frequency

```
text = "apple banana apple"

freq = {}

for word in text.split():
    freq[word] = freq.get(word, 0) + 1

print(freq)
```

Output:

```
{'apple': 2, 'banana': 1}
```

---

## Swap Keys & Values

```
d = {"a": 1, "b": 2}

swapped = {v: k for k, v in d.items()}
```

---

# 17. Mutable vs Immutable Keys

Valid keys:

```
d = {
    "name": "John",
    1: "one",
    (1, 2): "tuple"
}
```

Invalid keys:

```
d = {
    [1, 2]: "list"
}
```

Lists are mutable → not allowed.

---

# 18. Time Complexity (Important)

| Operation | Average Complexity |
|---|---|
| Access | O(1) |
| Insert | O(1) |
| Delete | O(1) |
| Search | O(1) |
| Traversal | O(n) |

---

# 19. Quick Cheat Sheet

```
d[key]                  # Access
d[key] = value          # Add/Update
del d[key]              # Delete
d.get(key)              # Safe access
d.keys()                # All keys
d.values()              # All values
d.items()               # Key-value pairs
d.update(other_dict)    # Merge/update
d.pop(key)              # Remove key
d.clear()               # Empty dictionary
len(d)                  # Size
key in d                # Check existence
```

---

# Final Notes

Python dictionaries are one of the most powerful and commonly used data structures.

They are:
- Fast
- Flexible
- Easy to use
- Essential for real-world applications

Master:
- Accessing
- Updating
- Traversing
- Comprehensions
- Nested dictionaries
- Safe key handling

These concepts are heavily used in:
- APIs
- JSON handling
- Data science
- Web development
- Machine learning
- Automation
s
