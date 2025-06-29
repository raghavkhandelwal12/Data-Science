# Table of Contents

* [Informal Introduction to Python](#informal-introduction-to-python)
* [Examples](#examples)
* [Using Python as a Calculator](#using-python-as-a-calculator)
* [Numbers](#numbers)
* [Text](#text)
* [Multi-line Strings](#multi-line-strings)

---

<h2 id="informal-introduction-to-python">Informal Introduction to Python</h2>

* When reading Python code, you’ll often encounter examples like this:

```python
>>> 2 + 2
4
```

- The `>>>` is called a `prompt`. It means you should type what comes after it `(2+2)`.
- The number `4` is the result that python gives you back. You don't need to type that part.

**You may also see multi-line blocks like this:**

```
>>> if True:
...     print("Hello")
...
Hello
```

* `...` indicates a continuation line, part of a code block.
* Pressing Enter on an empty line tells Python you’re done with the block.

<h2 id="examples">Examples</h2>

```python
# This is a comment
spam = 1  # Another comment
         # And one more
text = "# This is not a comment because it's inside quotes."
print(text)
```

**Output:**

```python
# This is not a comment because it's inside quotes.
```

<h2 id="using-python-as-a-calculator">Using Python as a Calculator</h2>

- Let's try some simple Python commands. Start the interpreter and wait for the primary prompt, `>>>`. (It should not take long).

<h2 id="numbers">Numbers</h2>

- The interpreter acts as a simple calculator: we can type an expression at it and it will write the value. Expression syntax straightforward : The operators `+, -, *, and /` can be used to perform `arithmetic,` parentheses `(())` can be used for grouping.
- In your terminal just type `Python` to use interpreter as a calculator.

```python
>>> 2 + 2
4
>>> 50 - 5 * 6
20
>>> (50 - 5 * 6) / 4
5.0
>>> 8 / 5
1.6
```

* Integers like `2, 4, 20` have type `int`. Numbers with decimals like `5.0, 1.6` have type `float`.
*  Division `(/)` always returns a `float`. To do `Floor division` and get an integer result we can use `//` operator ; to calculate the remainder we can use `%`.

```python
>>> 17 / 3
5.666666666666667
>>> 17 // 3
5
>>> 17 % 3
2
>>> 5 * 3 + 2
17
```

* Power operator:

```python
>>> 5 ** 2
25
>>> 2 ** 7
128
```

- The `equal sign(=)` is used to assing value to variables. 

```python
>>> width = 20
>>> height = 5 * 9
>>> width * height
```
**Output**
```
900
```

- If a variable  is not `defined (assign a value), trying to use it will give an error`.


```python
>>> n # try to access an undefined variable
```
**Output**
```
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
NameError: name 'n' is not defined
```

- There is full support for floating point; operators with mixed type operands convert the `interger operand to floating point`.

```
>>> 4 * 3.75 - 1

```
**Output**
```
14.0

```

- In interactive mode, The last printed expression is assigned the variable `_`. This means that when we are using Python as a desk calculator, it is somewhat easier to continue calculations.

```python
>>> tax = 12.5 / 100
>>> price = 100.50
>>> price * tax
12.5625
>>> price + _
113.0625
>>> round(_, 2)
113.06
```

- The variable should be treated as read-only by the user. Don't explicitly assign a value to it - You would create an indeprendent local variable with the same name masking the built-in variable with its magic behavior.

- In addition to `int and float`. Python supports other type of numbers, such as `Decimal and Fraction`. Python also has built-in support for `complex numbers` and uses the `j or J suffix` to indicate the imaginary part `(e.g. 3+5j)`

<h2 id="text">Text</h2>

- Python can manipulate text (represented by type `str, so-called strings`) as well as numbers. This includes `character "!", words "rabbits", names "Paris", sentences "Got your back", etc`. They can be enclosed in `single quotes('...')` or `double quotes("...")` with the same result

```
>>> 'spam eggs' #single quotes
```
**Output**
```
'spam eggs'
```
```
>>> "Paris rabbit got you back : !yay!" # double quotes
```
**Output**
```
'Paris rabbit got you back : !yay!'
```
```
'1975' # digits and numerals enclosed in quotes are also strings
```
**Output**
```
'1975'
```

- To quote a quote, we need to "escape" it be preceeding it with `\`. Alternatively, we can use the other type of quotation marks.


```
>>>'doesn\'t' # use \' to escape single quotes
```
**Output**
```
"doesn't"
```

```
>>>"doesn't" # ... or use double quotes instead
```
**Output**
```
"doesn't"
```

```
' "Yes," they said.'
```
**Output**
```
' "Yes," they said.'
```

- In The Python  shell, the string definition and output string can look different. The `print()` function produces a more readable output, by omitting the enclosing quotes and by printing escapes and special characters.

```
s = 'First line. \nSecond line.' #\n means new line
s #without  print(), special characters are included in the string
```

**Output**
```
'First line.\nSecond line.'
```
```
print(s)
```
**Output**
```
First line
Second line
```

- If we don't want characters prefaced by `\` to be interpreted as special characters, we can use raw strings by adding an `r` before the first quotes.

```
print('C:\some\name') # here \n means newline!
```
**Output**
```
C:\some
ame
```

```
print(r'C:\some\name') #note the r before the quote
```
**Output**
```
C:\some\name
```

<h2 id="multi-line-strings">Multi-line Strings</h2>

# Multi-line Strings

- We can write strings that go over `mulitiple lines` by using `triple quotes-like """ or '''`.
- New line(pressing enter) are `included in the string`.
- If you don't want the line break, you can add a `backslash(\)` at the end of the line to ignore the enter.

```python
print("""
Usage: thingy [OPTIONS]
    -h              Display this usage message
    -H hostname     Hostname to connect to
""")
```

**Output:**

```
Usage: thingy [OPTIONS]
    -h              Display this usage message
    -H hostname     Hostname to connect to
```

- Strings can be `concatendated(glued together)` with the `+ operator, and repeated with *`.

```
# 3 time 'raghav', followed by 'khandelwal'
3 * 'raghav' + 'khandelwal'
```
**Output**
```
'raghavraghavraghavkhandelwal'
```
- Two or more strings literals `(i.e. the ones enclosed between quotes)` next to each othe are automatically concatenated.

```
'Py' 'thon'
```
**Output**
```
'Python'
```
- The feature is particularly useful when we start break long strings.

* Joining strings using parentheses:

```
text = ('Put several strings with parentheses ' 
        'to have them joined them together.')
print(text)
```

**Output**
```
Put several strings with parentheses to have them joined them together.
```
- This only works with two literals through, not with variables or expressions:
```
prefix = 'Py'
prefix 'thon' # can't concatenate a variable and a string literal.
```
**Output**
```
Cell In[16], line 2
    prefix 'thon' # can't concatenate a variable and a string literal.
           ^
SyntaxError: invalid syntax
```

- If we want to concatenate variables or a variable and a literal, use `+`.

```
prefix = 'Py'
prefix + 'thon'
```

**Output**
```
'Python'
```

- Strings can be indexed(subscripted), with the first character `having index 0`. There is no seperate character type; a character is simply a string size one.

```
word = 'Python'
word[0] # character in position 0
```
**Output**
```
'P'
```
```
word[5] # character in position 5
```
**Output**
```
'n'
```
- Indices may also be negative numbers, to start counting from the right.

```
word = 'Python'
word[-1] # last character
```
**Output**
```
'n'
```
```
word[-2] #second character
```
**Output**
```
'o'
```

**Note that since -0 is the same as 0, negative indices start from -1**.

- In addition to indexing, slicing is also supported. While `indexing is used to obtain individual character, slicing allows to obtain a substring`.


```
word = 'Python'
word[0:2] # Characters from position 0(included) to 2(excluded).
```
**Output**
```
'Py'
```

```
word = 'Python'
word[2:5] # characters from position 2(included) to 5 (excluded)
```
**Output**
```
'tho'
```
- Slice indices have useful default; an omitted first index defaults to zero, an omitted second index defaults to the size of the string being sliced.

```
word = 'Python'
word[:2] # character from the begining to position 2(excluded)
```
**Output**
```
'Py'
```

```
word = 'Python'
word[4:] # character from position 4(included) to the end
```
**Output**
```
'on'
```
```
word = 'Python'
word[-2:]  # characters from the second-last(included) to the end
```
**Output**
```
'on'
```

- Now how the `start is always included, and the end always excluded`. This makes sure that `s[:i] + s[i:]` is always equal to s.
```
word = 'Python'
word[:2]+word[2:]
```
**Output**
```
'Python'
```

- One ways to remember how slices work is to think of the indices as pointing between character, with the `left edge of the first character numbered 0. Then the right edge of the last character of a string of n character has index n, for example`.

* String slice diagram:

```
+---+---+---+---+---+---+
| P | y | t | h | o | n |
+---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
```

* Index errors and slicing safety:

```python
word[42]      # IndexError
word[4:42]    # 'on'
word[42:]     # ''
```
- The first row of number give the position `of the indices 0...6` in the string. The second row gives the corresponding `negative indices. ` the slice from `i to j` consist all characters between the edges labeled i and j , respectively.

- For non-negative indices, the length of a slice is the difference of the indices, if both are within bounds, `for examples the lenght of **word[1:3] is 2**`.

- **Attempting to use an index that is too large will result in an error**.

```
word = 'Python'
word[42] # the word only has 6 characters
```

**Output**
```
---------------------------------------------------------------------------
IndexError                                Traceback (most recent call last)
Cell In[28], line 2
      1 word = 'Python'
----> 2 word[42] 

IndexError: string index out of range
```

- **However, out of range slice indexes are handled gracefully when used for slicing.**

```
word = 'Python'
word[4:42]
```
**Output**
```
'on'
```

```
word = 'Python'
word[42:]
```
**Output**
```
''
```
- **Python strings cannot be changed - they are `immutable`. Therefore, assigning to an index position in the string results in an error.**

```
word = 'Python'
word[0]='J'
```
**Output**
```
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[31], line 2
      1 word = 'Python'
----> 2 word[0]='J'

TypeError: 'str' object does not support item assignment
```
- **If we need a different string, we should create a new one**.

```
word = 'Python'
'J' + word[1:]
```
**Output**
```
'Jython'
```

```
word = 'Python'
word[:2] + 'py'
```
**Output**
```
'Pypy'
```
- The built-in function `len()` returns the length of the string.
```
s = 'studfsaguaghasgagfg'
print(len(s))
```
**Output**
```
19
```

