# Python Lists and Copying (Beginner Guide)

## Table of Contents

* [Lists](#lists)
* [Indexing and Slicing Lists](#indexing-and-slicing-lists)
* [List Operations (Concatenation)](#list-operations-concatenation)
* [List Mutability](#list-mutability)
* [Appending to Lists](#appending-to-lists)
* [Simple Assignment (No Copy)](#simple-assignment-no-copy)
* [Shallow Copy](#shallow-copy)
* [Deep Copy](#deep-copy)
* [Assignment to Slices](#assignment-to-slices)
* [Length of List](#length-of-list)
* [Nested Lists](#nested-lists)
* [First Steps Towards Programming](#first-steps-towards-programming)

---

## Lists

In Python, a `list` is a way to group several values together. Think of it like a box that holds multiple items, written between square brackets `[]`, separated by commas.

```python
squares = [1, 4, 9, 16, 25]
print(squares)
```

**Output**

```
[1, 4, 9, 16, 25]
```

## Indexing and Slicing Lists

Like strings, lists can be indexed and sliced.

```python
squares = [1, 4, 9, 16, 25]
print(squares[0])
print(squares[-1])
print(squares[-3:])
```

**Output**

```
1
25
[9, 16, 25]
```

## List Operations (Concatenation)

Lists support operations like concatenation:

```python
squares = [1, 4, 9, 16]
squares + [36, 49, 64, 81, 100]
```

**Output**

```
[1, 4, 9, 16, 36, 49, 64, 81, 100]
```

## List Mutability

Unlike strings, which are immutable, lists are mutable. You can change their content.

```python
cubes = [1, 8, 27, 65, 125]
cubes[3] = 64
print(cubes)
```

**Output**

```
[1, 8, 27, 64, 125]
```

## Appending to Lists

You can add new items to the end using `.append()`:

```python
cubes = [1, 8, 27, 64, 125]
cubes.append(7**3)
print(cubes)
```

**Output**

```
[1, 8, 27, 64, 125, 343]
```

## Simple Assignment (No Copy)
**Simple assignment in Python never `copies data`. When you assign a list to a variable refer to the existing list. Any changes you make to a list through one variable will be seen through all other variable that refer to it.**

Assignment does not copy data:

```
rgb = ["Red", "Green", "Blue"]
rgba = rgb
id(rgb) == id(rgba)
```
**Output**
```
True
```
```
rgb = ["Red", "Green", "Blue"]
rgba = rgb
id(rgb) == id(rgba)
rgba.append('alph')
print(rgb)
```
**Output**
```
['Red', 'Green', 'Blue', 'alph']
```

```
rgb = ["Red", "Green", "Blue"]
rgba = rgb
print(rgba)
```
**Output**
```
['Red', 'Green', 'Blue']
```

**Explanation**
- `rgb` is a list with `3 items`.
- `rgba = rgb` does not create a new list.
- It just make `rgba` point to the same list as `rgb`.
- So now, both `rgb and rgba` refer to the same list in memory.

```
rgb = ["Red", "Green", "Blue"]
rgba = rgb
id(rgb) == id(rgba)
```
**Output**
```
True
```

**The `id()` function gives the memory address. Since both variables points to the same lists, their ids are equals.**.

**Modify the list using one Variable**

```
rgb = ["Red", "Green", "Blue"]
rgba = rgb
id(rgb) == id(rgba)
rgba.append("Alph")
print(rgb)
print(rgba)
```
**Output**
```
['Red', 'Green', 'Blue', 'Alph']
['Red', 'Green', 'Blue', 'Alph']
```
**Now we added `"Alph"` to the `rgba` list. But since `rgba` and `rgb` are the same list, this change also affects `rgb`.**

- Any changes through `rgba` will be visible through `rgb` too.

# What is Copy in Python?

- When we `copy` a list(or any object), we want to `create a new object` that has the `same content`. But how Python copies depends on how `deep` the structure is.

## Shallow Copy

- A `Shallow Copy` creates a `new outer object`, but does `not copy the inner objects`. Instead , it `reuses references` to the inner objects.

**Example : Shallow Copy with Simple Values(No Problem)**.
```
original = [1, 2, 3]
copy_list = original.copy()

copy_list[0] = 100
print("Original:", original)
print("Copy:", copy_list)
```
**Output**
```
Original: [1, 2, 3]
Copy: [100, 2, 3]
```
**Explanation**
- Each item is a number(immutable).
- `copy_list` is a `different list`, so changing it does not affect `original`.

**Example 2 : Shallow Copy with Nested List(Problem Happens)**
```
original = [1, [2, 3], 4]
copy_list = original.copy()
copy_list[1][0] = 999 # modify inner list
print("Original:", original)
print("Copy:", copy_list)
```
**Output**
```
Original: [1, [999, 3], 4]
Copy: [1, [999, 3], 4]
```
**Explanation**
- `original[1] and copy_list[1]` both point to the `same inner list [2, 3]`.
- When we changed `copy_list[1][0] to 999` it also change inside `original`.
  
## Deep Copy

- A `deep copy` creates a new `outer object` and also `recursively copies all inner object` Nothing is shared.

**How to create it**
- Use the `copy moduel`.
```
import copy
deep = copy.deepcopy(original)
```

**Example: Deep Copy with Nested Lists**
```
import copy
original = [[1, 2], [3, 4]]
deep = copy.deepcopy(original)
deep[0][0] = 99
print("Original:", original)
print("Deep:", deep)
```
**Output**
```
Original: [[1, 2], [3, 4]]
Deep: [[99, 2], [3, 4]]
```

- No changes to `original` -  The `inner lists` are `fully copied`.

**Check Memory Ids**
```
import copy
a = [[1, 2], [3, 4]]
shallow = a[:]
deep = copy.deepcopy(a)
print(id(a[0]) == id(shallow[0]))
print(id(a[0])==id(deep[0]))
```
**Output**
```
True
False
```
## Assignment to Slices

**Assignment to slices is also possible, and this can even change the size of the list or clear it entirely.**

```
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
print(letters)
```
**Output**
```
['a', 'b', 'c', 'd', 'e', 'f', 'g']
```

**Replace some values**
```
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
letters[2:5] = ['C', 'D', 'E']
print(letters)
```
**Output**
```
['a', 'b', 'C', 'D', 'E', 'f', 'g']
```
**Remove the elements from the lists**
```
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
letters[2:5] = []
print(letters)
```
**Output**
```
['a', 'b', 'f', 'g']
```
**Clear the list by replacing all the elments with an empty list**
```
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
letters[:]=[]
print(letters)
```
**Output**
```
[]
```

## Length of List

Use `len()` to get the number of items:

```python
letters = ['a', 'b', 'c', 'd']
print(len(letters))
```

**Output**

```
4
```

## Nested Lists

Lists can contain other lists:

```python
a = ['a', 'b', 'c']
n = [1, 2, 3]
x = [a, n]
print(x)
print(x[0])
print(x[0][1])
```

**Output**

```
[['a', 'b', 'c'], [1, 2, 3]]
['a', 'b', 'c']
b
```

## First Steps Towards Programming

- We can use Python for more complicated tasks than adding two and two together. For instance, we can write an initial sub-sequence of the `fibonacci series` as follows.

```
# Fibonacci series:
# The sum of two elements defines the next
a, b = 0, 1
while a<=10:
    print(a)
    a, b = b, a+b
```
**Output**
```
0
1
1
2
3
5
8
```

```
i = 256*256
print("the value fo i is", i)
```
**Output**
```
the value fo i is 65536
```

- **The keyword argument `end` can be used to avoid the `newline` after the output, or the `end the output with a different string`.

```
a,b = 0, 1
while a<1000:
    print(a, end = ',') #use the end to avoid new line
    a, b = b, a+b
```
**Output**
```
0,1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987,
```
