# Python Module Imports Demonstration

This document summarizes and demonstrates absolute and relative imports in Python using example modules from the provided directory structure.

---

## Absolute Imports

Absolute imports specify the full path from the project root.

Example modules from `lib/absolute_package`:

- `package1.module1`:

```python
def function1():
    print('Function 1 in module 1')
```

- `package2.subpackage1.module6`:

```python
def function1():
    print('Function 1 in module 6')
```

Using absolute imports, you can import and call these functions like:

```python
from package1 import module1
module1.function1()
# Output: Function 1 in module 1

from package2.subpackage1 import module6
module6.function1()
# Output: Function 1 in module 6
```

---

## Relative Imports

Relative imports use dot notation to specify location relative to the current module.

Example modules from `lib/relative_package`:

- `subpackage1.subpackage2.module1` (assumed):

```python
def function1():
    print('Function 1 from module1')
```

- `subpackage1.subpackage2.module2`:

```python
from .module1 import function1

function1()
# Output: Function 1 from module1

# Relative import of a sibling module
```

- `subpackage1.module3`:

```python
def function1():
    print('Function 1 from module3')
```

Relative imports allow cleaner imports when package structure changes.

Example usage of parent directory import (commented out in module2):

```python
from .. import module3

module3.function1()
# Output: Function 1 from module3
```

---

## Pros and Cons

- Absolute imports are clear and explicit about the resource location but can be verbose for deeply nested modules.

- Relative imports are shorter and allow package rearrangements without changing import statements but may reduce code readability and clarity for developers unfamiliar with the package structure.

---

## Usage Guidelines (PEP-8)

- Use absolute imports where possible for clarity.

- Use relative imports when module paths are long or cumbersome especially for nested packages.

- Avoid mixing styles within the same package.

---

This demonstration aims to clarify the concepts and usage of import styles using practical, runnable examples.
