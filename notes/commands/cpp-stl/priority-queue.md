# priority_queue

## Why Use It

- Heap adapter for always getting the current extreme element.
- Max-heap by default.
- Very common in greedy algorithms and Dijkstra variants.

## Core Syntax

```cpp
priority_queue<int> pq;
pq.push(5);
pq.push(10);
pq.top();
pq.pop();
```

## Min-Heap

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
```

## Competitive Programming Patterns

- Dijkstra's algorithm.
- K largest / K smallest elements.
- Scheduling and greedy selection.

## Pitfalls

- `top()` does not remove the element.
- For custom ordering, define a comparator carefully.
