# queue

## Why Use It

- FIFO container adapter.
- Useful for BFS and level-order traversal.
- Usually backed by `deque`.

## Core Syntax

```cpp
queue<int> q;
q.push(1);
q.front();
q.pop();
```

## Competitive Programming Patterns

- Breadth-first search.
- Multi-source BFS.
- Sliding-window style queue logic.

## Pitfalls

- Access is only at the front and back.
- Check `q.empty()` before `front()` or `pop()`.
