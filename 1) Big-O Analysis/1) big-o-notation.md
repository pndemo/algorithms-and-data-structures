# Big-O Notation
When trying to characterize an algorithm’s efficiency in terms of execution time, independent of any
particular program or computer, it is important to quantify the number of operations or steps that the
algorithm will require. If each of these steps is considered to be a basic unit of computation, then the
execution time for an algorithm can be expressed as the number of steps required to solve the problem.
This can be done by expressing the number of assignment statements in an algorithm in form of a function
`T(n)`. However, the exact number of assignment statements is not as important as determining the most
dominant part of an function. In other words, as a the problem gets larger, some portion of the `T(n)`
function tends to overpower the rest. The dominant part in the end, is what is needed for comparison.
The order of magnitude function describes the part of `T(n)` that increases the fastest as the value of
`n` increases. Order of magnitude, often called Big-O and written as `O(f(n))` provides a useful
approximation of the actual number of steps in the computation. The function `f(n)` provides a simple
representation of the dominant part of the original `T(n)`. For example, considering an equation
`T(n) = 1 + n`. As `n` gets large, the constant `1` will become less and less to the final result. Also,
in `T(n) = 5n^2 + 27n + 1005`, as `n` gets large, `n^2` will become more significant as the other parts
get less significant. We would say then that the function `T(n)` has an order of magnitude `f(n)=n^2`, or
simply that it is `O(n^2)`. Sometimes the performance of an algorithm depends on the exact values of the
data rather than simply the size of the problem. For these kinds of algorithms we need to characterize
their performance in terms of best case, worst case or average case performance. In order to decide which
function is the dominant part of any `T(n)` function, we must see how they compare with one another as `n`
gets large. The table below shows the most common functions for Big-O.

| f(n)          | Name          |
| ------------- |:-------------:|
| 1             | Constant      |
| log n         | Logarithmic   |
| n             | Linear        |
| n log n       | Log Linear    |
| n^2           | Quadratic     |
| n^3           | Cubic         |
| 2^n           | Exponential   |
