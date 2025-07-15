# An Informal Introduction to Python

1. `Understanding the Python Prompt(>>> and ...)` :
    - When you are using the `Python interpreter(command-line mode)`, it shows special `symbols(called prompts)`.
    - `>>>` :  This is the `main prompt`. It tells you that Python is ready to take a `new command`.
    - `...` : This is the `secondary prompt`. It appears when your commands `spans multiple lines`, like a function or loop.
    ```
    >>>print("Hello")
    Hello
    ```
- In the above case:
    - You type: `print("Hello") after >>>`
    - Python shows output : `Hello`(without any prompt)
- If your are writing `multi-line code(like a function)` you must press enter `twice` to leave a blank line to tell python you are done.
```
>>> def greet(name):
...     print("Hello", name)
...     
>>> greet("Raghav")
Hello Raghav
```

2. `Using the "Copy" Button` : 
- In python you see `code blocks`.
- These have a `Copy button`(usually top-right corner).
- When you click it:
    - It `Copies only the code`(not the `>>>` prompts or the output).
    - You can paste it directly into your python editor or shell.
- This is useful to try code examples quickly without typing everythig manually.

3. `Comments in Python` : 
- A `comment` is a note you add to your code to explain what it does.
- In python, comments starts with a `#` symbol.
- Anything after `#` on the same line is `ignored by Python`(not executed).
- Comments helps humans understand the code but have not effect on how the code runs.

**Examples**:
```
# This is a comment
print("Hello") # This prints Hello
```
**Output**
```
Hello
```
- `Allowed` :
    - At the start of line : `# this is a comment`.
    - After code : `print("Hi") #say hi

- `Not Allowed` : 
    - Inside a string
```
print("This is # not a comment") # This works fine, the hash is part of the string
```
**Output**
```
This is # not a comment
```

4. `Should you type the Output?` :
- No. when you see example like this:
```
>>>2 + 2
4
```
- You type only `2 + 2`
- Python shows you `4` as output.
- Don't type the `4` 

```
# This is the First Comment
spam = 1 # and this is the another comment
         # ... and now a third comment
text = "# this is not a comemnt becuase it's inside quotes"
print(text)
```
**Output**
```
# this is not a comemnt becuase it's inside quotes
```

# Using Python as Calculator

1. `Numbers` : 
- Python works like a Calculator, you can type  math expressions, and it will show the result.
- You can use:
    - `+` for addition
    - `-` for subtraction
    - `*` for multiplication
    - `/` for division
- You can also use `parentheses ()` to control the order of operations.
```
>>>(2 + 3) * 4
20
```
- Python first adds `2 + 3` (inside parentheses), then multiplies by `4`.
```
>>>2 + 2 # Type this in your terminal 
4        # output 
>>>
>>>50 - 5*6  # Type this in your terminal
20           # Output
>>>
>>>(5o - 5*6) / 4 # Type this in your terminal
5.0               # Output
>>>
>>>8/5 #division always returns a floating point number
1.6    # Output
```
- In Pythn `Whole number like 2, 4, 20` are of type `int`, and numbers with `decimals like 5.0, 1.6` are of type `float`.
    
    - `Normal division /` always gives a `float`(decimal result).
    - Use `//` for `floor division`(get the whole number part).
    - Use `%` to get the `remainder` after divsion.

```
>>>17/3 # Classic division returns a float
5.666666666666667 # Output
>>>
>>>17//3 # Floor divison discard the fractional part
5        # Output
>>>
>>>17%3 # The % operator returns the remainder of the division
2       # Output
>>>
>>>5*3 + 2 #Floored quotient * divisior + remainder
17
```

- In python, use the `**` operator to calculate the `Power`.

```
>>>5**2 # 5 squared
25      # Output
>>>
>>>2**7 # 2 to the power of 7
128     # Output
```

## The Equal Sign `=` in Python

**What does `==` do?**
- In Python, the `=` sign is used to `assign a value to a variable.`
- This means you are telling python: "Store the value in this name".

```
variable_name = value
```
- The `left side` is the name you want to give(the variable).
- The `right side` is the value you want to store

**Example**
```
>>>x = 10
```
- This stores the number `10` in the variable `x`.
- Python `does not show any output` when you assign a value.
- But the value is stored - you can use it later.

``` 
>>>x # assign the x already which value is 10
10   # Output
>>>x+10 # Type your terminal
15      # Output
```

```
>>>width = 20 # assign the widht 
>>>height = 5*9 # assign the height
>>>widht * height # Multiply this
900              # Output
```

## Using a Variable Without Defining it

**What does it mean?**
- In Python, `you must assign value to a variable before using it`.
- If you try to use a variable `without assigning` it first, Python does not know what it is and gives an `error`.

```
>>>n # try to access an undefined variable
```
**Output**
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module> 
NameError: name 'n' is not defined 
```
## Mixing Integers and Floats in Python

**What does it mean?**

- Python fully supports floating-point numbers(like `3.14, 0.5 etc`). And when you use an `integer and a float` together in an operation, Python `automatically converts` the integer to a float to avoid losing decimal accuracy.

**Example**
```
>>>3 + 2.0 # Int and float operation
5.0        # Output float implicit conversion
```
- `3` is `int`, `2.0` is a `float`.
- Python converts `3` to `3.0` internally.
- So the result is `5.0` a float.

**Why does Python do this?**
- This is called `implicit type conversion(also known as type coercion)`.
- It helps prevent `loss of precision`.
```
>>>4 * 3.75 - 1
14.0    # Output
```

## Using Python as a Desk Calculator with `_`
- When you are working in `interactive mode`(like in Python shell or terminal), Python automatically saves the result of the `last printed expression` to special variable `_`.
- This is very helpful when using Python like a `calculator`, because it allows you to reuse the last result `without retyping it`.
```
>>>100+50 #TYPE your terminal
150       # Output
>>>_ *2
300
>>>_ - 25
275
```
**Explanation** :
- You add 100 and 50, and Python returns `150`.
- `_` now holds `150`, so  `_ * 2` gives `300`.
- `_` now holds `300`, so `_ -25` gives `275`.

# Why is this Useful?
- When doing quick calculations you can:
    - Avoid typing previous results manually.
    - Chain operations efficiently.
    - Use Python just like a normal calculator - but smarter.

**Important Notes** : 
- This behavior `only works in interactive mode`, like:
    - The python `REPL(run python in terminal)`.
    - IPython or Jupyter notebooks
- It does not work in `.py` scripts files automatically.
- `_` can be overwritten if you assign it directly.

```
>>>tax = 12.5/100 # Type the in our terminal
>>>price = 100.50 #Type the in our terminal
>>>price * tax    # Type the in our terminal
12.5625           # Output
>>>price + _      # _ this take the last expression result
113.0625          # output
>>>round(_,2)     # This only give the decimal of the 2
113.06
```
## The special variable `_` in Interactive Mode
- In Python's `interactive mode`(like when you open the terminal and type `python`), there are special built-in variable called `_(underscore)`/.

**What it Does?**
- `_` automatically stores the `result of the last printed expression`.
- You can use it to continue calculations without retyping the previous result.

**Important Warning**:
- Do not assign a value to `_` manually.
`If you do something like` :
```
_ = 10
```
- You `override` the special behavior. After that `_` will no longer hold the last result automatically - it will just be a regular variable.

## Other Number Types in Python
- Besides the common `int`(integers) and `float`(decimal numbers), Python also supports more specialized number types.

**Decimal**: 
    - Used for `precise decimal calculations(e.g for money)`.
    - Regular floats can have rounding errors. `Decimal` avoid that.

```
from decimal import Decimal
print(Decimal('0.1') + Decimal('0.2')) #output 0.3
```
**Fraction** : 
    - Used for `exact fractions(like 1/3 or 2/5)`.
    - Keeps numbers in fractional form, not decimal.

```
from fraction import Fraction
print(Fraction(1,3) + Fraction(1, 3)) #Output 2/3
```
**Complex Number** : 
    - Used for `imaginary and complex number` calculations.
    - Syntax : `a + bj` where
        - `a` = real part
        - `b` = imaginary part
        - `j` or J is used to mark the imaginary part.

**Example**
```
z = 3 + 5j
print(z.real) # Output 3.0
print(z.imag) # Output 5.0
```
**Output**
```
3.0
5.0
```

# Text In Python

## What is Text in Python?
- In Python `text` is called a `string` - its data type is `str`(short for string). A string is just a `sequence of characters`, like:
    - `A single Character : '!`.
    - `A Word : 'rabbit'`.
    - `A names : 'Paris`.
    - `A sentence : 'Got your back.'`
    - `Emoji or symbols : 'Yay!'`.

### How to Writes Strings in Python?
- We can create a string by putting the text inside either:
    - `Single Quotes : 'Hello'`
    - `Double Quotes : "Hello"`

**Example** : 
```
>>>'spam eggs' # single quotes
'spam eggs'    # Output
>>>"Parris rabbit got your back !)!Yay!" # Double quotes
'Paris rabbit got your back :)! Yay!'    # Output
>>> '1975' # digits and numerals enclosed in quotes are also strings
'1975'     # Output
```  

**What does "Quoting a Quote" Mean?**
- When you are including a quote `inside another quote`. you may run into problem because the interpreter or system may confuse the `inner quote` with the `outer one`.

**Example without escaping** : 
```
print("she said, "Hello!"")
```
**Output**
```
Cell In[1], line 1
    print("she said, "Hello!"")
          ^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
```
**Solutions** : 
- `A. Escape the inner quote(using \)` : In many language like `Python, Javascript and C we can use backslash(\)` to escape the quotation marks.
```
print("She said, \"Hello!\"")
```
**Output** 
```
She said, "Hello!"
```
- `B. Use the other type of quote(single vs. Double)` : Most languages allow both `'` and `"` for strings so you can alternate.
```
print('she said, "Hello"')
```
**Output**
```
she said, "Hello"
```
```
>>>'doesn\'t' # use \' to escape the single quotes
"doesn't"     # Output
>>>"doesn't"  # ... or use double quotes inside
"doesn't"     # Output
>>>'"Yes, "they said.'
'"Yes, "they said.' 
```

# Python Shell vs `print()` - Key Difference
- When you type a string in the `Python shell,` is uses the `repr()` of the string.
    - `repr()` gives the `official representation of the string`.
    - It includes : 
        - Quotation marks`(' or ")`.
        - Escape sequence`(\n,\t,\\ etc)`.

- `print()` uses the `str()` of the string
    - `str()` gives `human friendly version` of the string.
    - It renders escape characters(e.g. newline) as actual effect and `omits` the quotes

**Example**
**Python shell output(act like `repr()`):**

```
>>>"Hello\nWorld"
'Hello\nWorld'
```
**Explanation**
- Quotes are shown(`'...'`).
- `\n` is not interpreted - it shown literally.

**`print()` Output(acts like `str()`)**
```
>>>print("Hello\nWorld")
Hello
World
```
**Explanation**
- No quotes.
- `\n` is interpreted - it becomes a newline.

```
>>>s = 'First line. \nSecondline.' # \n means new line
>>>s # Without print(), special character are include in the string
'First line. \nSecondline.'
>>>print(s) # with print(), special characters are interpreted, so \n produces new line
First line.
Secondline
```
# What are `Raw Strings` in Python?
- In Python, `raw strings` are defining by prefixing the string with an `r` or `R` before the operning quotation mark:
```
r"your string here".
```
- This tells Python : `Don't treat backslashes(\) as escape charaters` just keep them as is.

## Why Use Raw Strings?
- Normally, in regular strings, backslashes are `escape characters`.
```
>>>"C:\newfolder"
'C:\newfolder' # Output this is use `repr()`
```
- This can cause problems:
    - `n`  is interpreted as newline.
    - `\t` is interpreted as `tab`.

```
>>>print("C:\newfolder")
```
**Output**
```
C:
ewfolder 
```

## Raw strings fixes this:
```
>>>print(r"C:\newfolder")
```
**Output**
```
C:\newfolder
```
- The backslashes are preserved `literally`, exact as typed.

## Common use Cases
1. `File Paths` : Avoid `\\` or accidental escapes.
2. `Regular Expression` : Avoid double escaping like `\\d` 
3. `Window Registry` : `Registry paths often have many \`

```
print('C:\some\name') #here \n means new line
```
**Output**
```
C:\some
ame
```
```
print(r'C:\smome\name')  # Note the r beore the quotes
```
**Output**
```
C:\smome\name
```
# What are Multi-line Strings in Python?
- Python allows you to create string literals that span `multiple line` using:
    - `Triple double quotes """..."""`
    - `Triple single quotes '''...'''`.
- These are typically used for:
    - Long blocks of text.
    - Docstrings(function/method documentation)
    - Preserving newline and formatting.

**Basic syntax**
```
multi_line = """This is a 
multi-line string"""
print(multi_line)
```
**Output**
```
This is a 
multi-line string
```
- The newline character `\n` is automatically included.
- No need for `\n` explicitly - pressing enter inside the triple quotes suffices.

## Controlling Newline with Backslash(\)
- If you don't want the newline at the end of the line use a `backslash(\)`  at the end of the line.
```
s = """This is a \
single logic line."""
print(s)
```
**Output**
```
This is a single logic line.
```
- The backslash `\` escapes the newline - the line `continuous on the next line` without inserting a line break.
- It's as if you wrote the string all on one line.

**Importing Details**
- Leading newline is included unless avoided
```
s = """
Hello
World"""
print(s)
```
**Output**
```
Hello
World
```
- Note the `blank first line`

**To prevent that start right after the opening quotes**
```
s = """Hello
World"""
print(s)
```

**Output**
```
Hello
World
```

**Multi-Line string with Newline**
```
text = """Line1
Line2
Line3"""
print(text)
```
**Output**
```
Line1
Line2
Line3
```
**Multi-line string without Newlines(using \)**
```
text = """Line 1\
Line 2 \
Line 3"""
print(text)
```
**Output**
```
Line 1Line 2 Line 3
```

# Concatenation(+) - Joining Strings
- The `+` operators `joins(contatenates)` two or more strings together to make a new string.
**Example**
```
a = "Hello"
b = "World"
result = a + " " + b
print(result)
```
**Output**
```
Hello World
```
- Strings are `immutable` in python so `a + b` creates a `new string`.
- Both operand `must be strings or you get a TypeError`.

# Repetition(*) - Repeat Strings
- The `*` operator repeats the string `n` times.
```
line = "=" * 10
print(line)
```
**Output**
```
==========
```
- You can use it to repeat any string.
```
print("Hi! " *3)
```
**Output**
```
Hi! Hi! Hi!
```
# Combined Example
```
pattern = ("*-" * 5) + "*"
print(pattern)
```
**Output**
```
*-*-*-*-*-*
```
**Example**
```
>>> # 3 times 'un', followed by 'ium'
>>> 3 * 'un' + 'ium'
'unununium' # Output
```

- If you write multiple strings `literal` side by side (no `+`, no `,` no `join()`), Python will automatically combine them into a `single string`.

```
text = "Hello, " "world!"
print(text)
```
**Output**
```
Hello, world!
```
- Python automatically combines `"Hello," and "world!" into "Hello, world!"`.

**How it works**
- This only work with `string literal`, not with `variables`.
```
message = "Welcome " "to " "Python!"
print(message)
```
**Output**
```
Welcome to Python!
```
**Does not work with variables**
```
a = "Hello,"
b = "World!"
msg = a b
print(msg)
```
**Output**
```
Cell In[25], line 3
    msg = a b
          ^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
```
# Common use case : Split Long string across lines
- You can break a long string into multiple lines without using `backslashes(\)` or string concatenation(+).

```
long_string = (
    "This is a long string "
    "That span multiple line "
    "But is still a single string."
)
print(long_string)
```
**Output**
```
This is a long string That span multiple line But is still a single string.
```
- No newlines are added unless you explicitly include them with `\n`.

**Comapare with `+` concatenation**:
```
msg = "Hello, " + "World!" # concatenation at runtime
print(msg)
```
**Output**
```
Hello, World!
```
**Wheras**
```
msg = "Hello, " "World!" # Concatenation at compile-time(faster)
```
```
>>>'Py' 'thon'
'Python'
```
- This features is particularly useful when you want to break long strings.
```
>>>text = ('Put several strings within parentheses '
            'to have them joined together')
>>>text
'Put several srings within parentheses to have them joined together'.
```

- This only works with two literals though, not with variables or expressions.
```
>>>prefix = 'Py'
>>>prefix 'thon' # can't concatenate a variable and a string literal
```
**Output**
```
File "<stdin>", line 1
    prefix 'thon'
           ^^^^^^
SyntaxError: invalid syntax
>>>
```

```
>>>('un' * 3) 'ium'
```
**Output**
```
File "<stdin>", line 1
    ('un' * 3) 'ium'
               ^^^^^^
SyntaxError : Invalid syntax
```
- If you want to concatenate variable or a variable and a literal use `+`.
```
>>>prefix = 'Py'
>>>prefix + 'thon'
'Python'
```
# What Does "String Indexing" Mean?
- String can be `indexed(subscripted)` with the first character having index `0`. There is no seperate character type; a character simple a string of size one.
```
>>>word = 'Python'
>>>word[0] #Character in position 0
'P'
>>>word[5] #Character in position 5
'n'
```
- Indices may also be negative numbers, to start counting from the right.
```
>>>word = 'Python'
>>>word[-1] # last character
'n'
>>>word[-2] # second last charactre
'o'
>>>word[-6] 
'p'
```

**Note that since `-0` is the same as `0`, to start counting from the right.**

# String slicing
- In addition to indexing, `slicing is also supported`. While `indexing` is used to obtain `individual character`, slicing allows to obtain `a substring`.

```
>>>word = 'Python'
>>>word[0:2] #character from position 0(included) to 2(exclude)
'Py' # Output
>>>word[2:5] # characters from position 2(included) to 5 excluded.
'tho' #Output
```
- If you don't write `the first number`, Python `starts from the begining`. If you don't write the `second number`, python goes to the `end`.

```
>>>word = 'Python'
>>>word[:2] #character from the begining to position 2()
'Py'        # Output
>>>word[4:] #Character from position 4(include) to the end
'on'        #Output
>>>word[-2:] #Character from the second-last(included) to the end
'on'  # Output
```
- Note how the start is always included and the end always excluded. This makes sure that `s[:i] + s[i:] is always is eqaul to s`.
```
>>>word = 'Python'
>>>word[:2] + word[2:]
'Python'
>>>word[:4] + word[4:]
'Python'
```
- One way to remember how slices work is to think of the indices as pointing between characters with the left edge of first character numbered 0, then the right edge of the last character of a string of n character has index n.
**Example**
```
+---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
```
- The above code first row of numbers gives the position of the indices 0...6 in the string. The second rows gives the corresponding negative indices. The slice from i to j consist of all character between the edges labeled i and j repectively.

```
>>>word = 'Python'
>>>word[42] # the word only has 6 character
```
**Output**
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module> 
IndexError: string index out of range
```
- However out of range slice indexes are handled gracefully when used for slicing.
```
>>>word = 'Python'
>>>word[4:42]
'on'
>>>word[42:]
'' # Output
```

# Why strings are immutable in Python?
- In python, `strings are immutable`, meaning once a string is created, `you cannot change its character`. You can create a new string based on modification, but you can't alter the original string directly.

**Example fo Error**
```
text = 'hello'
text[0] = 'H'
print(text)
```
**Output**
```
TypeError: 'str' object does not support item assignment
```
## Correct way to Modify a string
- If you want to change a string(like capitalizing the first letter), you need to create a new string.
```
text = 'hello'
new_text = "H" + text[2:]
print(new_text)
```
**Output**
```
Hello
```
## Why are strings Immutable?
1. `Hashing & Performance` : Immutable strings can be used as dictionary keys and stored in sets.
2. `Thread-Safety` : No unexpected changes in string during concurrent execution.
3. `Memory Optimization` : Python reuse string object for efficiency.

```
>>>word = 'Python'
>>>word[0] = 'J'
```
**Output**
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```
```
>>>word = 'Python'
>>>word[2:] = 'py'
```
**Output**
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```
- If you need a different string you should create a new one
```
>>>word = 'Python'
>>>'J' + word[1:]
'Jython' #Output
>>>word[:2] + 'py'
'Pypy' #Output
 



