# list

## Why Use It

- Doubly linked list with stable iterators.
- Useful when you insert and erase in the middle very often.
- Rare in competitive programming compared with `vector` and `deque`.

## Core Syntax

```cpp
list<int> l = {1, 3, 5};
auto it = next(l.begin());
l.insert(it, 2);
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Push front | `l.push_front(x)` | O(1) |
| Push back | `l.push_back(x)` | O(1) |
| Insert | `l.insert(it, x)` | O(1) once iterator is known |
| Erase | `l.erase(it)` | O(1) |
| Splice | `l.splice(...)` | O(1) |

## Competitive Programming Patterns

- Rarely the best default.
- Useful when you must move nodes between containers without copying.

## Pitfalls

- No random access: `l[i]` does not exist.
- Poor cache locality makes it slower than vectors in many cases.
