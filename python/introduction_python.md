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

* The `>>>` symbol is the Python prompt. Type the expression (`2 + 2`) after the prompt.
* The result (`4`) is Python’s response—you don't need to type it.

**You may also see multi-line blocks like this:**

```python
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

* Start the interpreter and wait for the `>>>` prompt.
* You can perform arithmetic directly in the interpreter.

<h2 id="numbers">Numbers</h2>

* Python can be used as a simple calculator. Operators like `+`, `-`, `*`, and `/` are used for arithmetic. Use parentheses `()` for grouping.

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

* Variable assignment:

```python
>>> width = 20
>>> height = 5 * 9
>>> width * height
900
```

* Accessing undefined variables:

```python
>>> n
NameError: name 'n' is not defined
```

* Mixed type operations:

```python
>>> 4 * 3.75 - 1
14.0
```

* Using `_` to access the last result:

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

* Python supports `int`, `float`, `Decimal`, `Fraction`, and `complex` (e.g., `3 + 5j`).

<h2 id="text">Text</h2>

* Python supports string values:

```python
>>> 'spam eggs'
'spam eggs'
>>> "Paris rabbit got you back : !yay!"
'Paris rabbit got you back : !yay!'
>>> '1975'
'1975'
```

* Escaping quotes:

```python
>>> 'doesn\'t'
"doesn't"
>>> "doesn't"
"doesn't"
>>> ' "Yes," they said.'
' "Yes," they said.'
```

* Newlines and `print()`:

```python
s = 'First line.\nSecond line.'
s
# 'First line.\nSecond line.'
print(s)
# First line.
# Second line.
```

* Raw strings (avoid escape characters):

```python
print('C:\\some\\name')
# C:\some\name
print(r'C:\some\name')
# C:\some\name
```

<h2 id="multi-line-strings">Multi-line Strings</h2>

* Using triple quotes for multi-line strings:

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

* String repetition and concatenation:

```python
3 * 'raghav' + 'khandelwal'
# 'raghavraghavraghavkhandelwal'
'Py' 'thon'
# 'Python'
```

* Joining strings using parentheses:

```python
text = ('Put several strings with parentheses '
        'to have them joined together.')
print(text)
# Put several strings with parentheses to have them joined together.
```

* Concatenating variable and literal using `+`:

```python
prefix = 'Py'
prefix + 'thon'
# 'Python'
```

* String indexing:

```python
word = 'Python'
word[0]    # 'P'
word[5]    # 'n'
word[-1]   # 'n'
word[-2]   # 'o'
```

* String slicing:

```python
word[0:2]    # 'Py'
word[2:5]    # 'tho'
word[:2]     # 'Py'
word[4:]     # 'on'
word[-2:]    # 'on'
word[:2] + word[2:]  # 'Python'
```

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

* Strings are immutable:

```python
word[0] = 'J'       # TypeError
'J' + word[1:]      # 'Jython'
word[:2] + 'py'     # 'Pypy'
```

* Get the length of a string:

```python
s = 'studfsaguaghasgagfg'
print(len(s))  # 19
```
