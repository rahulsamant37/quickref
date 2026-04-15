# utilities

## Why Use Them

- Small helper types and functions that show up everywhere in contest code.
- They reduce boilerplate and make code easier to read under time pressure.

## Core Toolkit

| Utility | Use |
|---|---|
| `pair` | Two related values |
| `tuple` | Multiple values with different types |
| `optional` | Value may be absent |
| `variant` | One of several types |
| `lambda` | Inline function object |
| `move` | Enable move semantics |
| `swap` | Exchange values |

## Competitive Programming Patterns

### pair

```cpp
pair<int, int> p = {1, 2};
cout << p.first << ' ' << p.second;
```

### tuple

```cpp
auto t = make_tuple(1, "x", 2.5);
auto [a, b, c] = t;
```

### lambda

```cpp
auto cmp = [](const pair<int, int> &x, const pair<int, int> &y) {
  return x.second < y.second;
};
```

### optional

```cpp
optional<int> x;
if (!x) x = 7;
```

### move and swap

```cpp
string s = "hello";
vector<string> v;
v.push_back(move(s));
swap(v[0], v[1]);
```

## Pitfalls

- Use `auto [a, b]` only when structured bindings are allowed by the compiler version.
- `move` does not move by itself; it casts to an rvalue reference.
