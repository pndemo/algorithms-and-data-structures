# Anagram Detection
A good example problem for showing algorithms with different orders of magnitude is the classic
anagram detection problem for strings. One string is an anagram of another if the second is simply
a rearrangement of the first. For example, `heart` and `earth` are anagrams. The strings `python`
and `typhon` are anagrams as well. For the sake of simplicity, we will assume that the two strings
in question are of equal length and that they are made up of symbols from the set of 26 lowercase
alphabetic characters. Our goal is to write a boolean function that will take two strings and
return whether they are anagrams.

##### Solution 1: Checking Off
Our first solution to the anagram problem will check the lengths of the strings and then to see
that each character in the first string actually occurs in the second. If it is possible to
checkoff each character, then the two strings must be anagrams. Checking off a character will be
accomplished by replacing it with the special Python value None. However, since strings in Python
are immutable, the first step in the process will be to convert the second string to a list.

```
def anagram_solution1(s1, s2):
    still_oK = True
    if len(s1) != len(s2):
        still_oK = False

    alist = list(s2)
    pos1 = 0

    while pos1 < len(s1) and still_oK:
        pos2 = 0
        found = False
        while pos2 < len(alist) and not found:
            if s1[pos1] == alist[pos2]:
                found = True
            else:
                pos2 = pos2 + 1

        if found:
            alist[pos2] = None
        else:
            still_oK = False

        pos1 = pos1 + 1

    return still_oK

print(anagram_solution1('abcd','dcba'))
```

The algorithm for the solution above has an O-complexity of O(n^2).

##### Solution 2: Sort and Compare
Another solution to the anagram problem will make use of the fact that even though s1 and s2
are different, they are anagrams only if they consist of exactly the same characters. So, if
we begin by sorting each string alphabetically, from a to z, we will end up with the same
string if the original two strings are anagrams.

```
def anagram_solution2(s1, s2)
  alist1 = s1.split('').sort.join
  alist2 = s2.split('').sort.join

  if alist1.downcase == alist2.downcase
    true
  else
    false
  end
end

puts(anagram_solution2('abcde','edcba'))
```

At first glance, one may be tempted to think that this algorithm is O(n). However, sorting is
typically O(n^2) or O(nlogn). Hence, the sorting operations dominate the algorithm.

##### Solution 3: Count and Compare
Our final solution to the anagram problem takes advantage of the fact that any two anagrams
will have the same number of a’s, the same number of b’s, the same number of c’s, and so on.
In order to decide whether two strings are anagrams, we will first count the number of times
each character occurs. Since there are 26 possible characters, we can use a list of 26 counters,
one for each possible character. Each time we see a particular character, we will increment the
counter at that position. In the end, if the two lists of counters are identical, the strings
must be anagrams.

```
def anagram_solution3(s1, s2):
    c1 = [0] * 26
    c2 = [0] * 26

    for i in range(len(s1)):
        pos = ord(s1[i]) - ord('a')
        c1[pos] = c1[pos] + 1

    for i in range(len(s2)):
        pos = ord(s2[i]) - ord('a')
        c2[pos] = c2[pos] + 1

    counter = 0
    match = True
    while counter < 26 and match:
        if c1[counter] == c2[counter]:
            counter += 1
        else:
            match = False

    return match

print(anagram_solution3('abcd','dcba'))
```

Again, the solution has a number of iterations. However, unlike the first solution, none of
them are nested. The first two iterations used to count the characters are both based on n.
The third iteration, comparing the two lists of counts, always takes 26 steps since there are
26 possible characters in the strings. This gives us an algorithm of O(n).
