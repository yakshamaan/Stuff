# Python Commands

This concise reference covers the commands demonstrated across the supplied Python, NumPy, and Matplotlib material. Examples use the conventional aliases `np` (NumPy), `pd` (Pandas), and `plt` (Matplotlib pyplot).

## 1. Core Python

| Command / syntax | Purpose | Quick example |
|---|---|---|
| `print()` | Writes a value to the console. | `print("Hello, World!")` |
| `input()` | Reads user input; the result is always a string. | `name = input("Name: ")` |
| `str()` | Converts a value to text for concatenation. | `"Age: " + str(35)` |
| `int()` | Converts compatible text or numbers to an integer. | `age = int(input("Age: "))` |
| `len()` | Returns the number of items or characters. | `len("Python")` |
| `abs()`, `pow()`, `max()`, `min()`, `round()` | Common numeric helpers. | `round(3.14159, 2)` |
| `floor()`, `ceil()`, `sqrt()` | Math functions after `from math import *`. | `sqrt(81)` |
| `+ - * / % // **` | Arithmetic: add, subtract, multiply, divide, remainder, floor-divide, power. | `10 % 3`, `2 ** 3` |

### Strings

| Command / syntax | Purpose | Quick example |
|---|---|---|
| `\n`, `\"`, `\\` | New line, literal quote, and literal backslash. | `print("Hi\nthere")` |
| `.lower()` / `.upper()` | Returns lower- or uppercase text. | `"Hello".upper()` |
| `.isupper()` | Tests whether all cased characters are uppercase. | `"ABC".isupper()` |
| `text[index]` | Reads a character by zero-based position. | `"Python"[0]` |
| `.index(value)` | Finds the first position of a character or substring. | `"Python".index("th")` |
| `.replace(old, new)` | Returns text with matching content replaced. | `"cat".replace("c", "h")` |

### Collections and control flow

| Command / syntax | Purpose | Quick example |
|---|---|---|
| `items[index]`, `items[-1]`, `items[start:end]` | List indexing, last item, and slicing. | `friends[1:3]` |
| `.extend()`, `.append()`, `.insert()` | Add multiple, final, or positioned list items. | `friends.append("Jim")` |
| `.remove()`, `.clear()`, `.pop()` | Remove matching, all, or last items. | `friends.pop()` |
| `.index()`, `.count()`, `.sort()`, `.reverse()`, `.copy()` | Locate, count, order, reverse, or independently copy a list. | `friends.sort()` |
| `(a, b)` | Creates an immutable tuple. | `coordinate = (4, 5)` |
| `dict[key]` / `.get(key, default)` | Reads a dictionary value; `get` can provide a fallback. | `months.get("Dec", "N/A")` |
| `if` / `elif` / `else` | Runs branches based on Boolean conditions. | `if score >= 50: print("Pass")` |
| `and`, `or`, `not` | Combines or negates conditions. | `is_ready and is_logged_in` |
| `== != > < >= <=` | Comparison operators; return `True` or `False`. | `age >= 18` |
| `while` | Repeats while a condition remains true. | `while i <= 10: i += 1` |
| `for ... in ...` | Iterates over items in a sequence. | `for name in friends: print(name)` |
| `range(stop)` / `range(start, stop)` | Produces integers; the stop value is excluded. | `range(3, 10)` |
| nested `for` loops | Visits values in nested structures such as 2D lists. | `for row in grid: for value in row: print(value)` |

### Functions, errors, files, modules, and classes

| Command / syntax | Purpose | Quick example |
|---|---|---|
| `def name(...):` | Defines a reusable function. | `def greet(name): print(name)` |
| `return value` | Ends a function and sends a result back. | `return num ** 3` |
| `try` / `except ErrorType` | Handles anticipated runtime errors. | `except ValueError: print("Invalid input")` |
| `open(path, mode)` | Opens a file: `r` read, `w` overwrite/write, `a` append, `r+` read/write. | `file = open("notes.txt", "r")` |
| `.readable()`, `.read()`, `.readline()`, `.readlines()` | Checks readability or reads whole/all/single lines. | `file.readline()` |
| `.write()` / `.close()` | Writes text or releases the file handle. | `file.write("Hello\n")` |
| `import module` / `from module import name` | Reuses code from a module. | `from chef import Chef` |
| `pip install`, `pip uninstall`, `pip --version` | Installs, removes, or checks Python packages. | `pip install numpy` |
| `class Name:` / `__init__` | Defines a custom type and its constructor. | `class Student: ...` |
| `self` | Refers to the current object in a method. | `self.gpa = gpa` |
| `class Child(Parent):` | Inherits behavior from a parent class. | `class ChineseChef(Chef): ...` |

> Note: when joining a string with a number, convert the number first: `"Age: " + str(age)`.

## 2. NumPy

```python
import numpy as np
```

| Command / syntax | Purpose | Quick example |
|---|---|---|
| `np.array(data)` | Creates a NumPy array from a list or nested lists. | `a = np.array([1, 2, 3])` |
| `.ndim`, `.shape`, `.dtype` | Inspect dimensions, size per dimension, and element type. | `matrix.shape` |
| `.itemsize`, `.size`, `.nbytes` | Inspect memory per item, item count, and total bytes. | `matrix.nbytes` |
| `dtype=` | Sets the element type at creation. | `np.array([1, 2], dtype="int16")` |
| `a[row, column]`, `a[:, col]` | Indexes an element, row, column, or slice. | `a[0, 1:6:2]` |
| `np.zeros()`, `np.ones()` | Creates zero- or one-filled arrays. | `np.zeros((2, 3))` |
| `np.full()`, `np.full_like()` | Creates arrays filled with a chosen value. | `np.full((2, 2), 99)` |
| `np.random.rand()` | Creates random floats from 0 up to 1. | `np.random.rand(2, 3)` |
| `np.random.random_sample()` | Random floats matching a supplied shape. | `np.random.random_sample(a.shape)` |
| `np.random.randint()` | Random integers; upper bound is excluded. | `np.random.randint(0, 10, size=(2, 2))` |
| `np.identity(n)` | Creates an `n x n` identity matrix. | `np.identity(3)` |
| `np.repeat(array, n, axis=)` | Repeats elements along an axis. | `np.repeat([1, 2], 2)` |
| `.copy()` | Creates an independent array copy. | `b = a.copy()` |
| `+ - * / **`, `+=` | Performs element-wise arithmetic. | `a ** 2` |
| `np.sin()`, `np.cos()` | Applies trigonometric functions element by element. | `np.sin(a)` |
| `np.matmul(a, b)` | Performs matrix multiplication. | `np.matmul(a, b)` |
| `np.linalg.det()` | Computes a matrix determinant. | `np.linalg.det(matrix)` |
| `np.min()`, `np.max()`, `np.sum()` | Calculates aggregate values; use `axis=` for rows/columns. | `np.sum(data, axis=0)` |
| `.reshape()` | Changes shape without changing item count. | `a.reshape(2, 2)` |
| `np.vstack()` / `np.hstack()` | Stacks compatible arrays vertically or horizontally. | `np.vstack([v1, v2])` |

## 3. Matplotlib

```python

import matplotlib.pyplot as plt
import numpy as np
import pandas as pd  # Imported for data-oriented work
```

| Command / syntax | Purpose | Quick example |
|---|---|---|
| `plt.plot(x, y)` | Draws a line graph. | `plt.plot(x, y)` |
| `plt.show()` | Displays the current figure. | `plt.show()` |
| `plt.title()`, `plt.xlabel()`, `plt.ylabel()` | Adds chart and axis labels. | `plt.title("Sales")` |
| `fontdict=` | Styles title or label text. | `plt.title("Sales", fontdict={"fontsize": 20})` |
| `plt.xticks()`, `plt.yticks()` | Sets tick positions or labels. | `plt.yticks([0, 2, 4, 6])` |
| `label=` + `plt.legend()` | Names plotted series and shows a legend. | `plt.plot(x, y, label="Revenue"); plt.legend()` |
| `color=`, `linewidth=`, `marker=`, `markersize=`, `markeredgecolor=`, `linestyle=` | Styles a line and its data points. | `plt.plot(x, y, color="red", linestyle="--")` |
| format string | Compact color, marker, and line style. | `plt.plot(x, y, "r.--")` |
| `np.arange(start, stop, step)` | Generates regularly spaced values; `stop` is excluded. | `x2 = np.arange(0, 4.5, 0.5)` |
| slicing | Plots selected portions of a series. | `plt.plot(x2[:5], x2[:5] ** 2, "r-")` |
| `plt.figure(figsize=, dpi=)` | Sets figure dimensions (inches) and resolution. | `plt.figure(figsize=(5, 3), dpi=300)` |
| `plt.savefig(path, dpi=)` | Exports the current figure. | `plt.savefig("mygraph.png", dpi=300)` |
| `plt.bar(labels, values)` | Draws a bar chart. | `bars = plt.bar(labels, values)` |
| `.set_hatch(pattern)` | Adds a pattern to a bar. | `bars[0].set_hatch("/")` |

## 4. Practical reminders

- Python indices start at `0`; negative indices count from the end.
- List and array slices exclude the end index.
- `range()` and `np.arange()` also exclude their stop values.
- Use `.copy()` for an independent NumPy array; `b = a` only creates another reference.
- Create the figure before plotting when you need a specific size or DPI, and call `savefig()` before closing or clearing it.
