# algorithms

## Why Use Them

- STL algorithms make common contest tasks shorter and less error-prone.
- They work on iterator ranges, so they compose well with vectors and arrays.

## Core Toolkit

| Algorithm | Use | Typical Complexity |
|---|---|---|
| `sort` | Order a range | O(n log n) |
| `lower_bound` | First `>= x` in sorted range | O(log n) |
| `binary_search` | Check presence in sorted range | O(log n) |
| `find` | Linear search | O(n) |
| `count` | Count matches | O(n) |
| `accumulate` | Sum / fold range | O(n) |
| `all_of` | Check every element | O(n) |
| `any_of` | Check at least one element | O(n) |
| `transform` | Map values | O(n) |
| `remove` | Shift unwanted values to the end | O(n) |
| `unique` | Remove consecutive duplicates | O(n) |
| `reverse` | Reverse range | O(n) |
| `next_permutation` | Enumerate permutations | O(n) per permutation |
| `iota` | Fill with increasing values | O(n) |

## Competitive Programming Patterns

### Sort + binary search

```cpp
sort(v.begin(), v.end());
bool ok = binary_search(v.begin(), v.end(), x);
auto it = lower_bound(v.begin(), v.end(), x);
```

### Unique sorted values

```cpp
sort(v.begin(), v.end());
v.erase(unique(v.begin(), v.end()), v.end());
```

### Sum and predicates

```cpp
long long sum = accumulate(v.begin(), v.end(), 0LL);
bool allPositive = all_of(v.begin(), v.end(), [](int x) { return x > 0; });
```

### Remove-erase idiom

```cpp
v.erase(remove(v.begin(), v.end(), 0), v.end());
```

## Pitfalls

- `remove` and `unique` do not actually shrink the container; always follow with `erase`.
- `lower_bound` and `binary_search` require a sorted range.
- Use the correct initial type with `accumulate`, for example `0LL` for long long sums.
