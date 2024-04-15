---
title: Misc. Notes
created: 2023-11-20T04:46
updated: 2024-04-14T00:24
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/🗒️-python/🔖/misc-notes
  - 🔴-academic/📚-educational-resource/format/website
  - 🔴-academic/📚-educational-resource/discipline/computer-science/programming-language/python
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resource::🗒️ Python::Misc. Notes
---

# Misc. Notes

---

> [!ABSTRACT]+ 
> Miscellaneous scratch notes pertaining to [Python](https://www.python.org/). [@WelcomePythonOrg2023]
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding Anki flashcards are available, enabling efficient revision and reinforcement of the concepts.

---

> [!INFO]+ 
> **Previous Note(s):**
> 

---

﹇<br>
Is there an equivalent of `return 0` like in C++? Or some way to indicate to the OS that the script ran successfully?

#anki-card 

In Python, successfully completing a script without encountering unhandled exceptions effectively indicates to the operating system that the program ended successfully.

However, if you want to explicitly send an exit status code, you can use `sys.exit()`. For example, `sys.exit(0)` means a clean, no-error exit. Here's how you can use it:

```python
import sys

def main():
    """Main function of the program."""
    print("Hello World!")
    sys.exit(0)


if __name__ == '__main__':
    main()
```

In this code, if the main() function runs without encountering any issues, the script will exit with status code 0, indicating the script ran successfully. If any error occurs, then the script will exit with a code different from 0, indicating an error. 

However, manually invoking `sys.exit(0)` isn't typically necessary unless you need to indicate a problem to outside scripts or systems. Simply allowing the script to run to completion results in a successful "exit status".

⌂
<br>﹈<br>^1701033794332

Manually invoking {1:`sys.exit(0)`} {2:isn't typically necessary} unless you {3:need to indicate a problem to outside scripts or systems}. Simply allowing the script {4:to run to completion} results in {a successful "exit status"}.
^1701033794342

﹇<br>
Is the following code valid?

```python
main:
    """Main function of the program."""
    print("Hello World!")

if __name__ == '__main__' -> int:
    main()
    return 0
```

#anki-card 

No, there are a couple of issues with the code. 

The corrections are made as follows:
- Python doesn't support `return` type annotations for scripts, _only_ for functions.
- The declaration of the `main` function is incorrect. It was declared as `main:`

```python
import sys

def main():
    """Main function of the program."""
    print("Hello World!")
    sys.exit(0)


if __name__ == '__main__':
    main()
```

⌂
<br>﹈<br>^1701155145777

﹇<br>
Conventionally, when trying to mimic C++, does it make sense to put `sys.exit(0)` at the end of the `if __name__ == 'main':` block, or would it be better to put it at the end of the `main()` function?

#anki-card

In Python, it’s not necessary to use `sys.exit(0)` at the end of your script. When a Python script finishes executing, it exits back to the command prompt, and the exit status is 0 by default, which indicates successful execution.

However, if you want to mimic C++ and explicitly indicate successful execution, you can put `sys.exit(0)` at the end of your `main()` function or at the end of the `if __name__ == '__main__':` block. Both are acceptable, and the choice depends on your personal preference or your project’s coding style guidelines.

Here’s how you can do it:

```python
import sys

def main():
    print("Hello, World!")
    sys.exit(0)

if __name__ == '__main__':
    main()
```

or

```python
import sys

def main():
    print("Hello, World!")

if __name__ == '__main__':
    main()
    sys.exit(0)
```

In both cases, `sys.exit(0)` will be called after `main()` finishes executing. If there’s an error in your `main()` function that causes it to exit prematurely, `sys.exit(0)` won’t be called, and the script will exit with a non-zero status, indicating an error, which is the same behavior as in C++.

⌂
<br>﹈<br>^1701197158323

﹇<br>
As of Apr. 09, 2024 10:46:44 AM, what is the significance of the `self` keyword in in following Python3 snippet? What does it allow us to do?

```python
class Solution:
	def sum(self, num1: int, num2: int) -> int:
		return num1 + num2
```

#anki-card 

The `self` keyword in Python is used to define instance methods within a class. It refers to the object instance itself that the method is called on.

In the provided code snippet:

```python
class Solution:
  def sum(self, num1: int, num2: int) -> int:
    return num1 + num2
```

The `sum` method is defined as an instance method within the `Solution` class. When you create an instance of the `Solution` class and call the `sum` method on it, the `self` keyword refers to that specific instance.

Here's a breakdown of how the `self` keyword works:

1. **Creating an Instance:**
	```python
	solution = Solution()
	```
    Here, you create an instance of the `Solution` class and assign it to the variable `solution`.
2. **Calling the Instance Method:**
	```python
	result = solution.sum(5, 3)
	```
	In this line, you call the `sum` method on the `solution` instance. When you do this, Python automatically passes the `solution` instance as the first argument to the `sum` method. This argument is assigned to the `self` parameter within the method definition.

Inside the `sum` method, you can access the instance's attributes and methods using the `self` keyword. For example, if you had another method within the `Solution` class that modifies the state of the object, you could use `self` to refer to that object's attributes.

In summary, the `self` keyword allows you to define methods that operate on specific instances of a class. It provides a way to create methods that can access and modify the data associated with a particular object.

⌂
<br>﹈<br>





---

## :EiZoteroItem: Bibliography

\[1\]
“Welcome to Python.org,” _Python.org_, Nov. 15, 2023. Available: [https://www.python.org/](https://www.python.org/). [Accessed: Nov. 20, 2023]

---

> [!INFO]+
> **Next Note(s):**

---
