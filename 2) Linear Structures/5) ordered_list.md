# Ordered List
The structure of an ordered list is a collection of items where each item holds a relative
position that is based upon some underlying characteristic of the item. The ordering is
typically either ascending or descending and we assume that list items have a meaningful
comparison operation that is already defined. Many of the ordered list operations are the same
as those of the unordered list.

- OrderedList() creates a new ordered list that is empty. It needs no parameters and returns
an empty list.
- add(item) adds a new item to the list making sure that the order is preserved. It needs the
item and returns nothing. Assume the item is not already in the list.
- remove(item) removes the item from the list. It needs the item and modifies the list.
Assume the item is present in the list.
- search(item) searches for the item in the list. It needs the item and returns a boolean
value.
- isEmpty() tests to see whether the list is empty. It needs no parameters and returns a
boolean value.
- size() returns the number of items in the list. It needs no parameters and returns an
integer.
- index(item) returns the position of item in the list. It needs the item and returns the
index. Assume the item is in the list.
- pop() removes and returns the last item in the list. It needs nothing and returns an item.
Assume the list has at least one item.
- pop(pos) removes and returns the item at position pos. It needs the position and returns
the item. Assume the item is in the list.

To implement the OrderedList class, we will use the same technique as seen previously with
unordered lists. Once again, an empty list will be denoted by a head reference to None.

```
class OrderedList:
    def __init__(self):
        self.head = None

    def search(self,item):
        current = self.head
        found = False
        stop = False
        while current != None and not found and not stop:
            if current.getData() == item:
                found = True
            else:
                if current.getData() > item:
                    stop = True
                else:
                    current = current.getNext()

        return found

    def add(self,item):
        current = self.head
        previous = None
        stop = False
        while current != None and not stop:
            if current.getData() > item:
                stop = True
            else:
                previous = current
                current = current.getNext()

        temp = Node(item)
        if previous == None:
            temp.setNext(self.head)
            self.head = temp
        else:
            temp.setNext(current)
            previous.setNext(temp)

    def isEmpty(self):
        return self.head == None

    def size(self):
        current = self.head
        count = 0
        while current != None:
            count = count + 1
            current = current.getNext()

        return count
```
