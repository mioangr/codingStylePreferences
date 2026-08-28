# Coding Preferences

## General Principles

- Prefer readability over cleverness.
- Minimize dependencies.
- Every function should explain what it does.
- A short description should example what the blocks of code inside the function do.
- For standard functions of the language that are not commonly known by the developers, explain with a comment what they do.
- All class names should start with "c".
- Try to have one responsibility per class and minimize its dependencies.
- Closing braces or parenthesis:
  Ideally the closing element should be at the same ident as the opening element.
  Avoid having the closing element (bracket or parenthesis) at the same ident as the command it started it. For example:
  Instead of
  raise ConnectionError(
    f"Failed to connect to database '{self.filename}': {e}"
  ) from e
  use
  raise ConnectionError(
    f"Failed to connect to database '{self.filename}': {e}"
    ) from e
  or even better, keep it in the same line as the text is not too long:
  raise ConnectionError( f"Failed to connect to database '{self.filename}': {e}") from e
  

### General Principles for Python
- Add type hints where practical.
- Use explicit imports:
  import pandas, numpy, tensorflow
  instead of 
  import pandas as pd
  import numpy as np
  import tensorflow as tf

- use the full namespace when accessing functions, e.g. tensorflow.keras

- Use pathlib instead of os.path.

## Naming

- Variables: camelCase
- Functions: camelCase
- Configuration constants: store them at the beginning for the file and and prefix them with config_
