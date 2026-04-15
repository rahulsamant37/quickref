# deque

## Why Use It

- Fast push and pop at both ends.
- Good when you need queue-like behavior plus front insertions.
- Slightly less cache-friendly than `vector`.

## Core Syntax

```cpp
deque<int> d;
d.push_back(2);
d.push_front(1);
```

## Common Operations

| Operation | Syntax | Cost |
|---|---|---|
| Push back | `d.push_back(x)` | O(1) |
| Push front | `d.push_front(x)` | O(1) |
| Pop back | `d.pop_back()` | O(1) |
| Pop front | `d.pop_front()` | O(1) |
| Access | `d[i]` | O(1) |

## Competitive Programming Patterns

- Sliding window with front/back updates.
- 0-1 BFS uses `deque` heavily.

```cpp
deque<int> dq;
dq.push_back(start);
while (!dq.empty()) {
  int node = dq.front();
  dq.pop_front();
}
```

## Pitfalls

- Still not ideal for frequent middle insertions; use `list` only when you truly need iterator stability around inserts.
- Iterators may invalidate on some operations, so keep logic simple.
