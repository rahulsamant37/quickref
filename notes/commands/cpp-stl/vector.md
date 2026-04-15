# vector

## Why Use It

- The default container for most competitive programming problems.
- Contiguous memory, fast random access, and amortized O(1) append.
- Best for arrays that grow while you solve.

## Core Syntax

```cpp
vector<int> v;
vector<int> a(5);
vector<int> b(5, 7);
vector<int> c = {1, 2, 3};
```

## Common Operations

| Operation | Syntax | Cost | Notes |
|---|---|---|---|
| Append | `v.push_back(x)` | Amortized O(1) | Most common operation |
| Remove last | `v.pop_back()` | O(1) | Requires non-empty vector |
| Access | `v[i]` | O(1) | No bounds check |
| Safe access | `v.at(i)` | O(1) | Throws on invalid index |
| Size | `v.size()` | O(1) | Returns `size_t` |
| Clear | `v.clear()` | O(n) | Keeps capacity |
| Resize | `v.resize(n)` | O(n) | Adds default values if growing |
| Reserve | `v.reserve(n)` | O(1) amortized | Prevents repeated reallocations |
| Iterate | `for (auto &x : v)` | O(n) | Use references when modifying |

## Competitive Programming Patterns

### Build an array fast

```cpp
vector<int> a(n);
for (int i = 0; i < n; ++i) cin >> a[i];
```

### Sort and deduplicate

```cpp
sort(v.begin(), v.end());
v.erase(unique(v.begin(), v.end()), v.end());
```

### Prefix sums

```cpp
vector<long long> pref(n + 1, 0);
for (int i = 0; i < n; ++i) pref[i + 1] = pref[i] + a[i];
```

### 2D vector

```cpp
vector<vector<int>> grid(n, vector<int>(m, 0));
```

## Pitfalls

- `push_back` can invalidate pointers, references, and iterators after reallocation.
- `vector<bool>` is specialized and often awkward; prefer `vector<char>` or `vector<int>` for flags.
- Call `reserve` when you know the approximate size.
- Use `long long` when sums may exceed `int`.
