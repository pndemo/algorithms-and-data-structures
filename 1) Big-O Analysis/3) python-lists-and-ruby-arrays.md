# Python Lists
The designers of Python had many choices to make when they implemented the list data structure.
Each of these choices could have an impact on how fast list operations perform. To help them
make the right choices they looked at the ways that people would most commonly use the list data
structure and they optimized their implementation of a list so that the most common operations
were very fast. Of course they also tried to make the less common operations fast, but when a
trade-off had to be made the performance of a less common operation was often sacrificed in
favor of the more common operation. Two common operations are indexing and assigning to an
index position. Both of these operations take the same amount of time no matter how large the
list becomes. When an operation like this is independent of the size of the list they are O(1).
The following table shows the Big-O efficiency of Python list operations.

| Operation        | Big-O Efficiency |
| ---------------- |:----------------:|
| index []         | O(1)             |
| index assignment | O(1)             |
| append           | O(1)             |
| pop()            | O(1)             |
| pop(i)           | O(n)             |
| insert(i, item)  | O(n)             |
| del operator     | O(n)             |
| iteration        | O(n)             |
| contains (in)    | O(n)             |
| get slice [x:y]  | O(k)             |
| del slice        | O(n)             |
| set slice        | O(n+k)           |
| reverse          | O(n)             |
| concatenate      | O(k)             |
| sort             | O(n log n)       |
| multiply         | O(nk)            |

# Ruby Arrays
Ruby arrays are analogous to Python lists. They represent lists of data in programs. Once you
have data in an array, you can sort it, remove duplicates, reverse its order, extract sections
of the array, or search through arrays for specific data. You can also convert an array to a
string, transform one array of data into another, and roll up an array into a single value. The
table below shows the most common operations and their complexity.

| Operation        | Big-O Efficiency |
| ---------------- |:----------------:|
| index []         | O(1)             |
| index assignment | O(1)             |
| append           | O(1)             |
| pop()            | O(1)             |
| pop(i)           | O(n)             |
| insert(i, item)  | O(n)             |
| delete operator  | O(n)             |
| iteration        | O(n)             |
| contains (in)    | O(n)             |
| get slice (x, y) | O(k)             |
| delete slice     | O(n)             |
| set slice        | O(n+k)           |
| reverse          | O(n)             |
| concatenate      | O(k)             |
| sort             | O(n log n)       |
| multiply         | O(nk)            |
