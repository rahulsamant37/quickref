# map

## Why Use It

- Sorted key-value store.
- Good when order matters or you need predecessor/successor by key.
- A go-to structure for counting and indexed lookup with ordering.

## Core Syntax

```cpp
map<string, int> freq;
freq["apple"]++;
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Insert/update | `m[key] = value` | O(log n) |
| Find | `m.find(key)` | O(log n) |
| Erase | `m.erase(key)` | O(log n) |
| Lower bound | `m.lower_bound(key)` | O(log n) |

## Competitive Programming Patterns

- Frequency tables when order is useful.
- Coordinate compression with ordered keys.
- Sweep line events.

```cpp
map<int, int> cnt;
for (int x : a) cnt[x]++;
```

## Pitfalls

- `m[key]` creates the key if it does not exist.
- Prefer `unordered_map` if you only need average O(1) lookups and order is irrelevant.
