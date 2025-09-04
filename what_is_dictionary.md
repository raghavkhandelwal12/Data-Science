# What is a Dictionary

- `Dictionary` in Python  are `mapping types` that store `key-value pairs similar to  arrays or maps in other langugage`. Each `Keys` must be `unique` and `each keys maps to value of any type(e.g string, tuple, list)`

## Creating the Dictionary
- To create the dictionary we use the `curly bracket ({})`

**Example** : 
```
mydict = {
    "marks" : [90, 20, 30],
    "student_name" : ["Ram", "Raju", "Ramkesh"]
}
```
- This above code to use to create the Python dictionary

## Key Features of Python Dictionary

- `Dictionary` to a collection of `key-value pairs`.You use dictionaries to store data in the form of a `mapping`.

- The `keys are unique` (there are no duplicates).`Keys must be immutable types (like str, int and tuple )`.Keys are case-sensitive, two keys of same identical string might represent different values.

- The values can be any `data type numbers, strings, or lists`.

- `Dictionary is ordered which means it contains specific order to store elements`.

- Dictionaries are `mutable(you can add, update, or remove items after creations)`.

- Unlike `list/tuples(which use numeric indexes)`, dictionaries uses `keys to access values`.

**Example** :
```
person = {"name": "abc", "age", 25}
print(person["name"]) # This print the person name which is abc
```
**Output**
```
abc
```
- Dictionaries can hold `other dictionaries`(nested dictionaries)

**Example** : 
```
# The student is one dictionary
student = {
    "name" : "abc",
    # This contain another dictionary which name is marks
    "marks" : {"math" : 90, "science" : 85}
}
```

## Time Complexities of Python Dictionary

**Access elements by key (O(1))** : The time complexity of retrieving a values by its `key` in a dictionary is `O(1)`. This is because dictionaries use a `hash table` internally which take constant time
**Example** : 
```
# Create a dictionary
dict = {'aa' : 1, 'bb' : 2, 'cc' : 3}
# Access value by key
val = dict['bb']
print(val)
```
**Output**
```
2
```
**Explanation Why O(1)** : Hash tables use the hash of the key to find memory location which enables direct access.

**Example** 
```
# Duplicates not allowed : Dictionary cannot have two items with the same key

mydict = {
    "brand" : "Ford",
    "model" : "Mustang",
    "year" : 1964,
    "year" : 2020 # This print only the last year value
}
print(mydict) 
```
**Output**
```
{'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
```
## Dictionary Length
- To determine how many items a dictionary use the `len()` function
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Anita],
}

print(len(student))  # print the length 2
```
**Output** : 
```
2
```
## Access Items
- Access to dictionary item use `square bracket`.

- we can also use access dictionary item `get()` that will give the same result.

**Example** : 
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Anita"],
}
x = student['names'] # this print only the names of the students
print(x)
print(student.get['names']) # This also give the same result
```
**Output** 
```
['Aman', 'Anita']
['Aman', 'Anita']
```

## Get keys
- The `keys()` method return a list of all the keys.
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Anita"],
}
x = student.keys()
print(x)
```
**Output**
```
dict_keys(['roll_no', 'names'])
```
- we can change after creating the dictionary

**Example** 
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Anita"],
}
x = student.keys()
print(x) # before changes

student['age'] = [10, 20]
print(x) # After change
```
**Output**
```
dict_keys(['roll_no', 'names'])
dict_keys(['roll_no', 'names', 'age'])
```
## Get Values and Get Items
- The `values() method return a list of all values and items() method will return each item in a dictionary as tuple in a list`.

**Example** : 
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Anita"],
}
x = student.values() # this give the all values
y = student.items() # this give the key and values both
print(x)
print(y)
```
**Output**
```
dict_values([[101, 102], ['Aman', 'Anita']])
dict_items([('roll_no', [101, 102]), ('names', ['Aman', 'Anita'])])
```

## Dictionary methods

1. `Changes values` : we can change values of specific item.

**Example** : 
```student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Abc"],
    "year" : 1900
}
student["year"] : 2000 # change the value
print(student['year'])
```
```
2000
```
2. `Update Dictionary` : The `update()` method will update the dictionary with the items. 

```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Abc"],
    "year" : 1900
}
student.update({"year" : 2020}) # update the years value
print(student)
```

**Output**
```
{'roll_no': [101, 102], 'names': ['Aman', 'Abc'], 'year': 2020}
```

3. `Adding items` : we can add items into a dictionary

**Example** :
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Abc"],
    "year" : 1900
}
student['age'] = [30, 20] # add a key and value
print(student)
```
**Output**
```
{'roll_no': [101, 102], 'names': ['Aman', 'Abc'], 'year': 1900, 'age': [30, 20]}
```

4. `Remove Dictionary Items` : To remove dictionary items there are several method.

**Example** : 
```
student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Abc"],
    "year" : 1900
}
student.pop('year') # remove the year items 
print(student)
```
**Output**
```
{'roll_no': [101, 102], 'names': ['Aman', 'Abc']}
```
### Python loop Dictionaries

**Loop Through dictionaries** : We can access the dictionary items using the loop

```student = {
    "roll_no": [101, 102,],
    "names": ["Aman", "Abc"],
    "year" : 1900
}
for x in student:
    print(student[x])
```
**Output**
```
[101, 102]
['Aman', 'Abc']
1900
```

## Nested Dictionaries
- A dictionary can contain dictionaries, called nested dictionaries.
```
myfamily = {
  "child1" : {
    "name" : "Emil",
    "year" : 2004
  },
  "child2" : {
    "name" : "Tobias",
    "year" : 2007
  },
  "child3" : {
    "name" : "Linus",
    "year" : 2011
  }
}

print(myfamily)
```
**Output** 
```
{'child1': {'name': 'Emil', 'year': 2004}, 'child2': {'name': 'Tobias', 'year': 2007}, 'child3': {'name': 'Linus', 'year': 2011}}
```

# Python code merge two dictionaries 

**Problem** : There are two dictionaries our task is to combine and added values of common keys in result

## Naive method to combine two dictionary Adding

```
# Python program to combine two dictionary
# adding values for common keys
# initializing two dictionaries
dict1 = {'a': 12, 'for': 25, 'c': 9}
dict2 = {'Geeks': 100, 'geek': 200, 'for': 300}


# adding the values with common key
for key in dict2:
    if key in dict1:
        dict2[key] = dict2[key] + dict1[key]
    else:
        pass
        
print(dict2)
```
**Output** :
```
{'Geeks': 100, 'geek': 200, 'for': 325}
```

**Explanation** :

1. `First we assign two dictionaries` :
    - `dict1 = dict1 = {'a': 12, 'for': 25, 'c': 9}`
    - `dict2 = {'Geeks': 100, 'geek': 200, 'for': 300}`

2. `Start the loop over `dict2` : 
    - The loop take the each key from `dict2`:1st → 'Geeks', 2nd → 'geek', 3rd → 'for'. 

3. `Checking if the key is present also dict1` : 
    - `Using: if key in dict1`

4. `Case 1 : Key is common in both dictionaries` : 
    - Add values : `dict2[key] = dict2[key] + dict1[key]`.
    - Example : `for key 'for' :300(from dict2) +25(from dict1) = 325`.

5. `Case2 : Key is not common` :
    - If they from `dict2` is not in `dict`, do nothing(pass).
    - `Example : 'Geeks' and 'geek' are not in dict1, so their values unchanged.`

6. `After loop finishes` : 
    - Only the common key `for` got updated.
    - Other keys remains same.

7. `Final output` : 
```
{'Geeks': 100, 'geek': 200, 'for': 325}
```

