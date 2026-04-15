# C++ STL Quick Reference

Use with:
- `ref stl` -> open this index
- `ref stl-list` -> list all supported STL quick-access topics
- `ref vector` -> jump directly to the `vector` note

## Fast Map

Containers:
- vector
- deque
- list
- array
- set
- map
- unordered_set
- unordered_map
- stack
- queue
- priority_queue

Algorithms:
- sort
- lower_bound
- binary_search
- find
- count
- accumulate
- all_of
- any_of
- transform
- remove
- unique
- reverse
- next_permutation
- iota

Other:
- iterators
- pair
- tuple
- optional
- variant
- lambda
- move
- swap

## Competitive Programming Tips

- Prefer `vector` for most sequences.
- Prefer `sort + binary_search/lower_bound` for offline queries.
- Use `unordered_map` and `unordered_set` when order does not matter and hashing is acceptable.
- Use `set`/`map` when you need order or predecessor/successor queries.
- Use `priority_queue` for greedy and Dijkstra-style selection.
- Use `iota`, `next_permutation`, and `accumulate` for short contest code.
