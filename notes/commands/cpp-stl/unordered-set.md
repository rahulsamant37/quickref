# unordered_set

## Why Use It

- Hash-based unique set.
- Average O(1) insert/find/erase.
- Best when order does not matter.

## Core Syntax

```cpp
unordered_set<int> s;
s.insert(5);
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Insert | `s.insert(x)` | Average O(1) |
| Find | `s.find(x)` | Average O(1) |
| Erase | `s.erase(x)` | Average O(1) |

## Competitive Programming Patterns

- Visited states in graphs.
- Deduplication when ordering is unnecessary.
- Fast membership checks.

## Pitfalls

- Worst-case can degrade.
- Hash collisions and bad custom hashes can hurt performance.
- Iteration order is unspecified.
