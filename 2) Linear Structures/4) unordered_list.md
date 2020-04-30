# Unordered List
The structure of an unordered list, is a collection of items where each item holds a
relative position with respect to the others. Some possible unordered list operations are
given below.
- List() creates a new list that is empty. It needs no parameters and returns an empty list.
- add(item) adds a new item to the list. It needs the item and returns nothing. Assume the
item is not already in the list.
- remove(item) removes the item from the list. It needs the item and modifies the list.
Assume the item is present in the list.
- search(item) searches for the item in the list. It needs the item and returns a boolean
value.
- isEmpty() tests to see whether the list is empty. It needs no parameters and returns a
boolean value.
- size() returns the number of items in the list. It needs no parameters and returns an
integer.
- append(item) adds a new item to the end of the list making it the last item in the
collection. It needs the item and returns nothing. Assume the item is not already in the
list.
- index(item) returns the position of item in the list. It needs the item and returns the
index. Assume the item is in the list.
- insert(pos, item) adds a new item to the list at position pos. It needs the item and
returns nothing. Assume the item is not already in the list and there are enough existing
items to have position pos.
- pop() removes and returns the last item in the list. It needs nothing and returns an item.
Assume the list has at least one item.
- pop(pos) removes and returns the item at position pos. It needs the position and returns
the item. Assume the item is in the list.

In order to implement an unordered list, we will construct what is commonly known as a
linked list. Recall that we need to be sure that we can maintain the relative positioning of
the items. However, there is no requirement that we maintain that positioning in contiguous
memory. It is important to note that the location of the first item of the list must be
explicitly specified. Once we know where the first item is, the first item can tell us where
the second is, and so on. The external reference is often referred to as the head of the
list. Similarly, the last item needs to know that there is no next item.

The basic building block for the linked list implementation is the node. Each node object
must hold at least two pieces of information. First, the node must contain the list item
itself. We will call this the data field of the node. In addition, each node must hold a
reference to the next node.

```
class Node:
    def __init__(self, initdata):
        self.data = initdata
        self.next = None

    def getData(self):
        return self.data

    def getNext(self):
        return self.next

    def setData(self, newdata):
        self.data = newdata

    def setNext(self, newnext):
        self.next = newnext
```

The unordered list is then built from a collection of nodes, each linked to the next by
explicit references. As long as we know where to find the first node, each item after that
can be found by successively following the next links. With this in mind, the UnorderedList
class must maintain a reference to the first node.

```
class UnorderedList:

    def __init__(self):
        self.head = None

    def isEmpty(self):
        return self.head == None

    def add(self,item):
        temp = Node(item)
        temp.setNext(self.head)
        self.head = temp

    def size(self):
        current = self.head
        count = 0
        while current != None:
            count = count + 1
            current = current.getNext()

        return count

    def search(self,item):
        current = self.head
        found = False
        while current != None and not found:
            if current.getData() == item:
                found = True
            else:
                current = current.getNext()

        return found

    def remove(self,item):
        current = self.head
        previous = None
        found = False
        while not found:
            if current.getData() == item:
                found = True
            else:
                previous = current
                current = current.getNext()

        if previous == None:
            self.head = current.getNext()
        else:
            previous.setNext(current.getNext())
```
