# iterators

## Why Use Them

- The common language for STL algorithms and containers.
- Helps you write generic code over ranges.

## Main Forms

- `begin()` / `end()` for forward traversal.
- `rbegin()` / `rend()` for reverse traversal.
- Iterator arithmetic works for random-access containers like `vector` and `array`.

## Utility Functions

| Utility | Use |
|---|---|
| `advance(it, n)` | Move iterator forward/backward |
| `distance(a, b)` | Count steps between iterators |
| `next(it, n)` | Get advanced copy |
| `prev(it, n)` | Get moved-back copy |

## Competitive Programming Patterns

```cpp
auto it = v.begin();
advance(it, 2);
cout << *it;
```

- Use `auto` to avoid verbose iterator types.
- Use reverse iterators when scanning from the back.

## Pitfalls

- Not all iterators support `it + n`.
- Invalidation rules depend on the container.
