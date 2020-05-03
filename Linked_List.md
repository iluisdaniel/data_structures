#Linked Lists

Python does not have a built-in linked list structure. However, it's very useful for intervew questions. Let's get started.

## Singly Linked List

### Structure 
A linked list is formed by nodes which are linked together like a chain. 

Each node holds data and also the pointer to the next node in the list.  Something to point out is that the absence of a backwards  pointer implies that there is a uni-directional link. This means that the whole list points in one direction and cannot point backwards. 

```
Head -> Node -> Node -> Node -> None

Node  [Data|Pointer]
```

### Code



**Node Class**

- Data: is the value you want to store in the node. Data could range from string, integer or user defined class. 
- Pointer: The next node in the list. This is Node type variable. 

``` python
class Node:
	def __init__(self, data):
		self.data = data           # Data field 
		self.next_element = None   # Pointer to the next node
```

**LinkedList Class** 

This class is used as a collection of Nodes. To keep track of the list we need a pointer to the first node in the list. 

The first node, better known as the the head node, does not contain any data and only points to the beginning of the list. We need to go through the head to reach our desired node in the list. 

```python
class linkedlist: 
	def __init__(self):
		self.head_node = None # Pointer to the first node
```

### Difference Between Linked Lists and Lists

The main difference between them is the way elements are inserted and removed. For Linked Lists, insertion and deletion happens in a constant amount of time. For Lists, it takes O(n). 

## Linked Lists Operations

### get_head

Returns the head of the list.

Time: O(1) since we are only returning the head. 

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
list = LinkedList()
print(list.get_head()) #returns none
```

### is_empty
	
Returns true if the list is empty.

Time: O(1) since we are only returning true if the head is None. 

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
	def is_empty():
		if self.head_node is None:
			return True
		else:
			return False
		
list = LinkedList()
print(list.is_empty()) #returns true
```

### Insertion at head

Insert a new element as the first element of the list. 

Time: the time complexity of inserting into the head is O(1) since we just point the head to a new node. 


Example: 

```
Head is None

Insert one Node

Node 1 is now next element of Head

Insert Node two

Node 2 is now next element of Head and Node 1 is next element of Node 2

Head -> Node2 -> Node1
```
**Code**

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
	def is_empty():
		if self.head_node is None:
			return True
		else:
			return False
			
	def insert_at_head(data):
		temp = Node(data)
		temp.next_element = self.head_node
		
		self.head_node = temp
		return self.head_node
		
list = LinkedList()
list.insert_at_head(data)
```

### Insertion at Tail

Inserts element at the end of the linked list

Time: Since you need to go through the entire list the time complexity is O(n).

Example: 

```
Head is None

Insert one Node

Node 1 is now next element of Head

Insert Node two

Node 2 is now next element of Node 1

Head -> Node1 -> Node2
```
**code**

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
	def is_empty():
		if self.head_node is None:
			return True
		else:
			return False
			
	def insert_at_head(data):
		temp = Node(data)
		temp.next_element = self.head_node
		
		self.head_node = temp
		return self.head_node
	
	def insert_at_tail(data):
		new_node = Node(data)
		
		if self.head_node is None:
			self.head_node = new_node
			return
		
		temp = self.head_node
		
		while temp.next_element:
			temp = temp.next_element
		
		temp.next_element = new_node
		return 
		
list = LinkedList()
list.insert_at_tail(data)
```

### Insert at index

TBD

### Search in a Singly Linked List

Searchers for an element with the specified data in the Linked List. 

There is no other apporch to traverse the whole list until we find the value. 

Time: Similar to lists and arrays it takes O(n) amount of time.

Algorithm:

1. Start at head
2. Traverse the list until you find the element or you reach the end of the list. 

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
	def is_empty():
		if self.head_node is None:
			return True
		else:
			return False
			
	def insert_at_head(data):
		temp = Node(data)
		temp.next_element = self.head_node
		
		self.head_node = temp
		return self.head_node
	
	def insert_at_tail(data):
		new_node = Node(data)
		
		if self.head_node is None:
			self.head_node = new_node
			return
		
		temp = self.head_node
		
		while temp.next_element:
			temp = temp.next_element
		
		temp.next_element = new_node
		return 
	
	def search(value):
		current_node = self.head_node
		
		while current_node:
			if current_node.data is value:
				return True
			current_node = current_node.next_element
		
		return False
		
list = LinkedList()
list.search(value)
```

### Delete at head

Deletes the first element of the list. If the list is empty it doesn nothing. 

Deletion is one example of where Linked Lists are more efficient than Arrays. You have to shift all the elements backwards if one element is deleted in Arrays. In Linked Lists, the node can be removed in constant time. 

Time Complexity: O(1)

Example:

```
list =  1 -> 2 -> 3

When 1 is removed, the head will point to the second element of the list. This case 2. 

list = 2 -> 3
```

**code**

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
	def is_empty():
		if self.head_node is None:
			return True
		else:
			return False
			
	def insert_at_head(data):
		temp = Node(data)
		temp.next_element = self.head_node
		
		self.head_node = temp
		return self.head_node
	
	def insert_at_tail(data):
		new_node = Node(data)
		
		if self.head_node is None:
			self.head_node = new_node
			return
		
		temp = self.head_node
		
		while temp.next_element:
			temp = temp.next_element
		
		temp.next_element = new_node
		return 
	
	def search(value):
		current_node = self.head_node
		
		while current_node:
			if current_node.data is value:
				return True
			current_node = current_node.next_element
		
		return False
		
	def delete_at_head():
		temp = self.head_node
		
		if temp is not None:
			self.head_node = temp.next_element
			temp.next_element = None
		return
		
		
list = LinkedList()
list.delete_at_head()
```

### Delete By Value

Deletes an element with the value specified. 

Time: O(n) since in the worst case you will have to go through the entire list. 

Algorithm: Similar to delete_at_head(), only difference is that we need to keep track of current and previous node. 

When we find the value in the current node, previous node will point to the next element of the current node. 

```python
import Node from Node

class LinkedList: 
	def __init__(self):
		self.head_node = None
	
	def get_head():
		return self.head_node
		
	def is_empty():
		if self.head_node is None:
			return True
		else:
			return False
			
	def insert_at_head(data):
		temp = Node(data)
		temp.next_element = self.head_node
		
		self.head_node = temp
		return self.head_node
	
	def insert_at_tail(data):
		new_node = Node(data)
		
		if self.head_node is None:
			self.head_node = new_node
			return
		
		temp = self.head_node
		
		while temp.next_element:
			temp = temp.next_element
		
		temp.next_element = new_node
		return 
	
	def search(value):
		current_node = self.head_node
		
		while current_node:
			if current_node.data is value:
				return True
			current_node = current_node.next_element
		
		return False
		
	def delete_at_head():
		temp = self.head_node
		
		if temp is not None:
			self.head_node = temp.next_element
			temp.next_element = None
		return
	
	def delete_value(value):
		current = self.head_node()
		previous = None
		
		if self.is_empty():
			print("List is empty")
			return False
		else:
			if current.data is value:
				current.delete_at_head()
				return True

		previous = current
		current = current.next_element
		
		while current is not None:
			if current.data is value:
				previous.next_element = current.next_element
				current.next_element = None
				print("Value was found and deleted")
				return True
			else:
				previous = current
				current = current.next_element
		
		print("Value was not in the list")
		return False
			
		
list = LinkedList()
list.delete_at_head()
```


## Double Linked Lists

The main difference between doubly and singly linked lists is that we keep track of next_element and previous_element. This makes DLL bi directional.

To implement this, we just need to add the pointer for the previous_element to our Node class. 

``` python
class Node:
    def __init__(self, data):
        self.data = data
        self.previous_element = None
        self.next_element = None 
```

It would look list this:

```
Head -> Node <-> Node <-> Node <-> None

Node  [Pointer|Data|Pointer]
```

### Tail Node

We already talked about head, and this is essential for every Linked List. But what if we keep a track of the tail node too. So we can aware of the head and the tail. 

To add the tail we just need to add another variable to the Linked List class. 

``` python
class LinkedList:
    def __init__(self):
        self.head_node = None
        self.tail_node = None 
```

Adding a tail will allow us to traverse a List both ways. Also, inserting at the tail will work as fast as inserting to the head. Time: O(1)

### Deleting Element

TBD

## Challenges

### length()

To calculate the length of a linked list we will have to traverse the entier list similar of what we  did in search(). 

Time complexity: O(n)

```python
import Node from Node
import LinkedList form LinkedList

def length(ls):
	current_node = ls.get_head()
	length = 0
	
	while current_node:
		length = length + 1
		current_node = current_node.next_element
	return length

```

### reverse()

If we just want to get the reverse list without change it the original we will have to create a temporal list, then we will have to traverse the original list staring at the tail. Each element will be add it to the tail of the temporal list. When the loop is finish we will just have to return the temporal list. 

Time complexity: O(n)

**Get the reverse of the list**

```python
import Node from Node
import LinkedList form LinkedList

def reverse(ls):
	if ls.is_empty():
		print("List is empty")
		return
	
	temp_list = LinkedList()
	current_node = ls.get_tail()
	
	while(current_node):
		temp_list.insert_at_tail(current_node.data)
		current_node = current_node.previous_element
	
	return temp_list
```

If we want to reverse the original list we will need to keep track of the previous node, current node, and next node while we traverse the list. 

- We start by saving the current node next_element to keep track of our next iteration. 
- The current node next_element will be assigned to the previous node we saved before. 
- The previous node becomes the current node to keep track in the next iteration. 
- The current node becomes the next node we saved before.  
- Then we assing the previous node to the head of the list. 

Time complexity: The algorithm runs in O(n) since the list is traversed once.

**Reverse the list**

``` python

import Node from Node
import LinkedList form LinkedList

def reverse(ls):
	if ls.is_empty():
		print("List is empty")
		return
	
	previous = None
	current = ls.get_head()
	next = None
	
	while current:
		next = current.next_element
		current.next_element = previous
		previous = current 
		current = next
		ls.head_node = previous
		

```

### Detect loop in a Linked List

A loop is formed when a node points to a previously traversed node in the linked list. 

```7(head)->5->2->7(head)```

**Floyd’s Cycle-Finding Algorithm**

This may be the fastest way to find a loop in a linked list.

``` python
def detect_loop(lst):
    # Keep two iterators
    onestep = lst.get_head()
    twostep = lst.get_head()
    while onestep and twostep and twostep.next_element:
        onestep = onestep.next_element  # Moves one node at a time
        twostep = twostep.next_element.next_element  # Skips a node
        if onestep == twostep:  # Loop exists
            return True
    return False

```

[source](https://www.techiedelight.com/detect-cycle-linked-list-floyds-cycle-detection-algorithm/)

### Find middle value

There different ways to go thourgh this challenge.

**Brute Force**

``` python
def find_middle(lst):
	if lst.is_empty():
		return None
	
	node = lst.get_head()
	mid = 0
	
	if node.length() % 2 == 0:
		mid = node.length() // 2
	else:
		mid = node.length() // 2 + 1
		
	for i in range(mid - 1):
		node = node.next_element
	
	return node.data
```

**Two Pointers**

More efficient solution. There will be two pointers that will work simultaneously. 

- Fast pointer will iterete two steps at a time. 
- Slow pointer will iterate one step at a time. 

When the fast pointer ends, the slow pointer will point to the middle. 

``` python

def find_middle(lst):
	if lst.is_empty():
		return None
	current = lst.get_head()
	if current.next_element == None:
		#only one node on the list so it returns its value. 
		return current.data
	
	middle_node = current
	current = current.next_element.nex_element
	
	while current:
		middle_node = middle_node.next_element
		current = current.next_element
		if current:
			current = current.next_element
	if middle_node:
		return middle_node.data
	return None
	
```

