# Lists

A list can hold elements with different data types.

`list = [“luis”, 28, 2020]`

## Initializing a list 

``` python
example = [“green”, 12]         # create a list of elements
emptyList = []                  # Create an empty list
sequenceList = list(range(10))  # create a list with numbers 

print(example)
print(emptyList)
print(sequenceList)
```

lists can hold strings, characters, integers, functions, and pretty much any other data type including other lists.

``` python
def hello():
	print("How re you doing?")
	
listExample = [1,2,3] 

mainList = ["Maria", listExample, hello, ["Another list"]]
```

## List Functions

### append()
Add element to the end of the list. Time: O(1)

```
example = [1,2,3]
example.append(4)
```

### insert()
Insert element to the list. insert(index, value). Time: O(n)

```
example = [1,2,3]
example.insert(0,0)
```

### remove()
Remove the given element. If the element is not found it will throw an error. If there are multiple elements with the same value, it will remove the first one found. Time: O(n)

```
l = [1,2,3]
l.remove(2)
```

### pop()
Remove the element at given index. If not element is given, it will remove the last one. Time: O(k) time where k < n.

```
l = [1,2,3]
l.pop()  # it will remove 3
l.pop(0) # it will remove 1
```

### reverse()
It reverses the list. Time O(n)

```
l = [1,2,3]
l.reverse()
```

## Slicing
In Python you can access a range of elements of a list using brackets and a colon. 

> list[start:end] all numbers between that range
> 
> list[start:] all numbers greater than start uptil the range
> 
> list[:end] all numbers less than end uptil the range
> 
> list[:] all numbers within the range

``` python
List = list(range(10))
print(List[0:4])  # 0, 1, 2, 3
print(List[3:])  # 3, 4, 5, 6, 7, 8, 9
print(List[:3])  # 0 1 2
print(List[:])  # 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
```
You can also specify the increment in the list indices and can also be negative. 


> list[start:stop:step] 

```python
List = list(range(10)) # define a range of values 0
print(List[0:9:2])  # 0, 2, 4, 6, 8  
print(List[9:0:-2])  # 9, 7, 5, 3, 1
```

You can also modify/add the content of a range. 

``` python
x = list(range(10))
print(x)   # 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
x[1:4] = [32, 19, 33]
print(x)  # 0, 32, 19, 33, 4, 5, 6, 7, 8, 9
```

del keywork is used to delete elements from a list. 

``` python
List = list(range(10))
print(List)  # 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
del List[::2]
print(List)  # 1, 3, 5, 7, 9
```

We can use negative indexing to the lists elements from the end.

```python
List = list(range(10))
print(List)
print(List[3:-2])  #3, 4, 5, 6, 7
```




