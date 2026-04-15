# unordered_map

## Why Use It

- Hash-based key-value store.
- Usually the fastest choice for counting and lookup.
- Very common in competitive programming.

## Core Syntax

```cpp
unordered_map<int, int> cnt;
cnt[x]++;
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Insert/update | `m[key] = value` | Average O(1) |
| Find | `m.find(key)` | Average O(1) |
| Erase | `m.erase(key)` | Average O(1) |

## Competitive Programming Patterns

- Frequency counting.
- Storing state to index mappings.
- Memoization by integer or string key.

```cpp
unordered_map<long long, int> seen;
if (!seen.count(x)) seen[x] = i;
```

## Pitfalls

- No ordering.
- Consider `reserve` when the input size is known.
- Use a custom hash for harder adversarial problems.
