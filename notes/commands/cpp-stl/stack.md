# stack

## Why Use It

- LIFO container adapter.
- Useful for DFS-like logic, monotonic stack problems, and parsing.
- Usually backed by `deque`.

## Core Syntax

```cpp
stack<int> st;
st.push(1);
st.top();
st.pop();
```

## Competitive Programming Patterns

- Parentheses matching.
- Next greater element.
- Histogram and monotonic stack problems.

## Pitfalls

- Only top access is allowed.
- Check `st.empty()` before `top()` or `pop()`.
