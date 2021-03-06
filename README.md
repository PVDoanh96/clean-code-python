#### Coding Style

We want your work to be readable by others; therefore, we encourage you to note the following:

- Please write in Python 3.7+.  __print()__ is a function in Python 3 so __print "Hello"__ will _not_ work but __print("Hello")__ will.
- Please focus hard on naming of functions, classes, and variables.  Help your reader by using __descriptive names__ that can help you to remove redundant comments.

________________________
#### Tip: Use meaningful names:

  - **Be descriptive and imply type** - E.g. for `booleans`, you can prefix with `is_` or `has_` to make it clear it is a condition. You can also use part of speech to imply types, like verbs for functions and nouns for variables.
  
  - **Be consistent but clearly differentiate**- E.g. `age_list` and `age` is easier to differentiate than `ages` and `age`.
  
  - **Avoid abbreviations and especially single letters** - (Exception: counters and common math variables) Choosing when these exceptions can be made can be determined based on the audience for your code. If you work with other data scientists, certain variables may be common knowledge. While if you work with full stack engineers, it might be necessary to provide more descriptive names in these cases as well.
  
  - **Long names != descriptive names** - You should be descriptive, but only with relevant information. E.g. good functions names describe what they do well without including details about implementation or highly specific uses.


________________________
  - Single letter variable names are _old school_ so please avoid them unless their life only spans a few lines.
  - Expand acronyms because __gcd()__ is hard to understand but __greatest_common_divisor()__ is not.
  - Please follow the [Python Naming Conventions](https://pep8.org/#prescriptive-naming-conventions) so variable_names and function_names should be lower_case, CONSTANTS in UPPERCASE, ClassNames should be CamelCase, etc.

- We encourage the use of Python [f-strings](https://realpython.com/python-f-strings/#f-strings-a-new-and-improved-way-to-format-strings-in-python) where the make the code easier to read.

- Please consider running [__psf/black__](https://github.com/python/black) on your Python file(s) before submitting your pull request.  This is not yet a requirement but it does make your code more readable and automatically aligns it with much of [PEP 8](https://www.python.org/dev/peps/pep-0008/). There are other code formatters (autopep8, yapf) but the __black__ formatter is now hosted by the Python Software Foundation. To use it,

  ```bash
  pip3 install black  # only required the first time
  black .
  ```

- All submissions will need to pass the test __flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics__ before they will be accepted so if possible, try this test locally on your Python file(s) before submitting your pull request.

  ```bash
  pip3 install flake8  # only required the first time
  flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
  ```

- Original code submission require docstrings or comments to describe your work.

- More on docstrings and comments:

  If you used a Wikipedia article or some other source material to create your algorithm, please add the URL in a docstring or comment to help your reader.

  The following are considered to be bad and may be requested to be improved:

  ```python
  x = x + 2	# increased by 2
  ```

  This is too trivial. Comments are expected to be explanatory. For comments, you can write them above, on or below a line of code, as long as you are consistent within the same piece of code.

  We encourage you to put docstrings inside your functions but please pay attention to indentation of docstrings. The following is a good example:

  ```python
  def sum_ab(a, b):
      """
      Return the sum of two integers a and b.
      """
      return a + b
  ```

- Write tests (especially [__doctests__](https://docs.python.org/3/library/doctest.html)) to illustrate and verify your work.  We highly encourage the use of _doctests on all functions_.

  ```python
  def sum_ab(a, b):
      """
      Returns the sum of two integers a and b
      >>> sum_ab(2, 2)
      4
      >>> sum_ab(-2, 3)
      1
      >>> sum_ab(4.9, 5.1)
      10.0
      """
      return a + b
  ```

  These doctests will be run by pytest as part of our automated testing so please try to run your doctests locally and make sure that they are found and pass:

  ```bash
  python3 -m doctest -v my_submission.py
  ```

  The use of the Python builtin __input()__ function is **not** encouraged:

  ```python
  input('Enter your input:')
  # Or even worse...
  input = eval(input("Enter your input: "))
  ```

  However, if your code uses __input()__ then we encourage you to gracefully deal with leading and trailing whitespace in user input by adding __.strip()__ as in:

  ```python
  starting_value = int(input("Please enter a starting value: ").strip())
  ```

  The use of [Python type hints](https://docs.python.org/3/library/typing.html) is encouraged for function parameters and return values.  Our automated testing will run [mypy](http://mypy-lang.org) so run that locally before making your submission.

  ```python
  def sumab(a: int, b: int) --> int:
      pass
  ```

- [__List comprehensions and generators__](https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions) are preferred over the use of `lambda`, `map`, `filter`, `reduce` but the important thing is to demonstrate the power of Python in code that is easy to read and maintain.

- Avoid importing external libraries for basic algorithms. Only use those libraries for complicated algorithms.
- If you need a third party module that is not in the file __requirements.txt__, please add it to that file as part of your submission.

### Source: [TheAlgorithms/Python](https://github.com/TheAlgorithms/Python/blob/master/CONTRIBUTING.md)
