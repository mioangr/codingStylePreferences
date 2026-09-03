# Coding Preferences

## General Principles

- Prefer readability over cleverness.

- Minimize dependencies.

- Every function should explain what it does.

- For standard functions of the language that are not commonly known by the developers, explain with a comment what they do.

- All class names should start with "c".

- Classes should be separated from the other code using a comment block just above the start of the class.
  The block should contain the class description and calling examples.

- Try to have one responsibility per class and minimize its dependencies.
  
- Closing braces or parenthesis:
  Ideally the closing element should be at the same ident as the opening element.
  Avoid having the closing element (bracket or parenthesis) at the same ident as the command it started it. For example:
  Instead of
  ```
  raise ConnectionError(
    f"Failed to connect to database '{self.filename}': {e}"
  ) from e
  ```
  use
  ```
  raise ConnectionError(
    f"Failed to connect to database '{self.filename}': {e}"
    ) from e
  ```
  or even better, keep it in the same line as the text is not too long:
  ```
  raise ConnectionError( f"Failed to connect to database '{self.filename}': {e}") from e
  ```
  

### General Principles for Python
- Add type hints where practical.
- Use explicit imports:
  ```
  import pandas, numpy, tensorflow
  instead of 
  import pandas as pd
  import numpy as np
  import tensorflow as tf
  ```
  
- use the full namespace when accessing functions, e.g. tensorflow.keras

- Use pathlib instead of os.path.

- avoid as much as possible the use of None.
  For example if a function is like myFunc(aParams: typing.Optional[typing.Sequence] = None)
  prefer to check the parameter for an empty list instead of comparing it with the None value.
  In many cases this will also remove the need to use the typing package.

- prefer the newer python functions.
  E.g. instead of typing.List use list

- avoid programming patterns that exist only in python (e.g. the decorator pattern that is done with python specific keywords or the collections.abc package).
  If possible stick to programming patterns that exist is standard OOP languages like c++
  
- To split a string in separate lines use the \ symbol instead of the parenthesis python trick.
  For example, instead of:
  ```
    calc_future_returns.description = (
        f"long text A {aVariable} "
        f"long text B {aVariable2}."
    )
  ```
  write:
  ```
    calc_future_returns.description =  \
        f"long text A {aVariable} "  \
        f"long text B {aVariable2}." 
  ```

## Commenting

- When adding your comments, prefix them with your name and the date you added them. This will help separate the AI comments from the developer's comments.

- When the comment is short and the code line it refers to is also short, put it at the end of the line instead of putting it above the line.

- When starting a block of code, add a short comment explaining what the is supposed to block do.

- When writing code that uses language idioms or calls functions that are not widely known by developers, add a comment to explain what the idioms of functions do.

- Do not delete any comments. If a comment is outdated and does no longer reflect that the code does, add a comment below it, using your name and your finding.


## Naming

- Variables: camelCase
- Functions: camelCase
- Configuration constants: store them at the beginning for the file and and prefix them with config_
