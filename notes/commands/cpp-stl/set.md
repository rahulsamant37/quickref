# set

## Why Use It

- Sorted unique keys.
- Good for ordered lookups, predecessor/successor, and distinct values.
- Typically implemented as a balanced tree.

## Core Syntax

```cpp
set<int> s;
s.insert(10);
s.erase(10);
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Insert | `s.insert(x)` | O(log n) |
| Erase | `s.erase(x)` | O(log n) |
| Find | `s.find(x)` | O(log n) |
| Lower bound | `s.lower_bound(x)` | O(log n) |
| Upper bound | `s.upper_bound(x)` | O(log n) |

## Competitive Programming Patterns

- Maintain distinct values under updates.
- Find next greater element in a dynamic set.
- Use `lower_bound` and `upper_bound` for interval logic.

```cpp
auto it = s.lower_bound(x);
if (it != s.end()) cout << *it;
```

## Pitfalls

- Faster than sorting repeatedly only when updates are interleaved with queries.
- For duplicates, use `multiset`.
