# Python Dictionaries
The second major Python data structure is the dictionary. Dictionaries differ from lists in
that you can access items in a dictionary by a key rather than a position. The get item and set
item operations on a dictionary are O(1). Another important dictionary operation is the contains
operation. Checking to see whether a key is in the dictionary or not is also O(1). The
efficiency of all dictionary operations is summarized below.

| Operation        | Big-O Efficiency |
| ---------------- |:----------------:|
| copy             | O(n)             |
| get item         | O(1)             |
| set item         | O(1)             |
| delete item      | O(1)             |
| contains (in)    | O(1)             |
| iteration        | O(n)             |

One important side note on dictionary performance is that the efficiencies we provide in the
table are for average performance. In some rare cases the contains, get item, and set item
operations can degenerate into O(n) performance.

# Ruby Hashes
Ruby hashes are also analogous to Python dictionaries and contain a collection of unique keys
and their values. Also called associative arrays, they are similar to Arrays, but where an
Array uses integers as its index, a Hash allows you to use any object type. Hashes enumerate
their values in the order that the corresponding keys were inserted. Also, hashes allow an
alternate syntax for keys that are symbols. Their common operations can compared to the Python
ones above.
