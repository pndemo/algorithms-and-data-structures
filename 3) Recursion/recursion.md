# Recursion
Recursion is a method of solving problems that involves breaking a problem down into smaller
and smaller subproblems until you get to a small enough problem that it can be solved
trivially. Usually recursion involves a function calling itself. While it may not seem like
much on the surface, recursion allows us to write elegant solutions to problems that may
otherwise be very difficult to program. Example problems to demonstrate recursion in Ruby
are shown below:

#### Sum of Numbers
```
def summation(numbers)
  if numbers_array.empty?
    return 0
  else
    number = numbers_array.pop
    return number + sum(numbers_array)
  end
end
```

#### Countdown
```
def countdown(n)
  return if n.zero?
  countdown(n-1)
end
```

All recursive algorithms must obey three important laws:
- A recursive algorithm must have a base case.
- A recursive algorithm must change its state and move toward the base case.
- A recursive algorithm must call itself, recursively.

First, a base case is the condition that allows the algorithm to stop recursing. A base
case is typically a problem that is small enough to solve directly. To obey the second law,
we must arrange for a change of state that moves the algorithm toward the base case. A
change of state means that some data that the algorithm is using is modified. Usually the
data that represents our problem gets smaller in some way. The final law is that the
algorithm must call itself. This is the very definition of recursion.

Below are some examples of recursion problems in Ruby.

#### Factorial of a number
```
def factorial(num)
  if (0..1).include?(num)
    return 1
  end
  num * factorial(num - 1)
end
```

#### Nth Fibonacci number
```
def fibonacci(number) 
  if number < 2
    number 
  else
    fibonacci(number - 1) + fibonacci(number - 2) 
  end
end
```
