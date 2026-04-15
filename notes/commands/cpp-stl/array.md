# array

## Why Use It

- Fixed size container with STL convenience.
- Safer and cleaner than raw arrays.
- Great for small compile-time sized buffers.

## Core Syntax

```cpp
array<int, 3> a = {1, 2, 3};
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Access | `a[i]` | O(1) |
| Fill | `a.fill(x)` | O(n) |
| Iterate | `for (auto &x : a)` | O(n) |

## Competitive Programming Patterns

- Small fixed-size DP states.
- Coordinate helpers or tiny buffers.

## Pitfalls

- Size is fixed at compile time.
- Use `vector` when the size depends on input.
