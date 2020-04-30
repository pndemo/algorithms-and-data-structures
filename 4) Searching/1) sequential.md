# Sequential Searching
When data items are stored in a collection such as a list, we say that they have a linear or
sequential relationship. Each data item is stored in a position relative to the others. In
Python lists, these relative positions are the index values of the individual items. Since
these index values are ordered, it is possible for us to visit them in sequence. This process
gives rise to our first searching technique, the sequential search. Starting at the first
item in the list, we simply move from item to item, following the underlying sequential
ordering until we either find what we are looking for or run out of items. If we run out of
items, we have discovered that the item we were searching for was not present.

```
def sequential_search(items, item):
    pos = 0
    found = False

    while pos < len(items) and not found:
        if items[pos] == item:
            found = True
        else:
            pos = pos+1

        return found
```

If the item is not in the list, the only way to know it is to compare it against every item
present. If there are n items, then the sequential search requires 𝑛 comparisons to discover
that the item is not there. In the case where the item is in the list, the analysis is not
so straightforward. There are actually three different scenarios that can occur. In the best
case we will find the item in the first place we look, at the beginning of the list. We will
need only one comparison. In the worst case, we will not discover the item until the very
last comparison, the nth comparison. What about the average case? On average, we will find
the item about halfway into the list; that is, we will compare against n/2 items. Recall,
however, that as n gets large, the coefficients, no matter what they are, become
insignificant in our approximation, so the complexity of the sequential search, is O(n).
