| Function                     | Description                                      |
|-----------------------------|--------------------------------------------------|
| `at(key)`                   | Access element with bounds checking              |
| `operator[](key)`           | Access/insert element without bounds checking    |
| `begin()`                   | Iterator to the first element                    |
| `end()`                     | Iterator to one past the last element            |
| `cbegin()`                  | Const iterator to the first element              |
| `cend()`                    | Const iterator to one past the last element      |
| `rbegin()`                  | Reverse iterator to the last element             |
| `rend()`                    | Reverse iterator to before the first element     |
| `crbegin()`                 | Const reverse iterator to the last element       |
| `crend()`                   | Const reverse iterator to before first element   |
| `empty()`                   | Check if map is empty                            |
| `size()`                    | Number of elements                               |
| `max_size()`                | Maximum number of elements possible              |
| `clear()`                   | Removes all elements                             |
| `insert()`                  | Insert element or range                          |
| `emplace()`                 | Construct and insert in-place                    |
| `emplace_hint()`            | Optimized in-place insert with hint              |
| `erase()`                   | Remove elements by key or iterator               |
| `swap()`                    | Swap contents with another map                   |
| `count(key)`                | Count elements with a specific key (0 or 1)      |
| `find(key)`                 | Iterator to element with key                     |
| `contains(key)`            | Check if key exists (C++20)                      |
| `equal_range(key)`          | Range of elements matching key                   |
| `lower_bound(key)`          | Iterator to first not less than key              |
| `upper_bound(key)`          | Iterator to first greater than key               |
| `key_comp()`                | Return key comparison function                   |
| `value_comp()`              | Return value comparison function                 |
| `merge()`                   | Merge contents from another map                  |
| `extract()`                 | Extract node handle                              |
| `insert_or_assign()`        | Insert or assign element                         |
| `try_emplace()`             | Insert if key doesn't exist                      |
| `get_allocator()`           | Get allocator object                             |
