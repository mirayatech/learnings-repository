## Data Types

| Data Type | Description                            | Example          |
| --------- | -------------------------------------- | ---------------- |
| int       | Integer numbers                        | 10               |
| float     | Floating-point numbers                 | 10.5             |
| str       | String; a sequence of characters       | "Hello, World!"  |
| bool      | Boolean; True or False                 | True             |
| list      | Ordered, mutable sequence of objects   | [1, 2, 3]        |
| tuple     | Ordered, immutable sequence of objects | (1, 2, 3)        |
| set       | Unordered collection of unique objects | {1, 2, 3}        |
| dict      | Collection of key-value pairs          | {'a': 1, 'b': 2} |

## Notice

- true or false need to be uppercase (True/False), otherwise it will be treated as a variable name

## Dynamic Typing

- python si highly fkexible reassigning variables to different type
-

## None

- `None`: a special value that represents nothingness
- Purpose of `None` is python version of `null` in other languages
- Must have a captial N, otherwise it will be treated as a variable name

## Converting Data Types

- `str()`: converts to string

  - Example: `str_value = str(10)` # Converts integer 10 to string "10"

- `int()`: converts to integer

  - Example: `int_value = int("10")` # Parses string "10" to integer 10

- `float()`: converts to float

  - Example: `float_value = float("10.5")` # Parses string "10.5" to float 10.5

- `bool()`: converts to boolean

  - Example: `bool_value = bool(1)` # True, because 1 is truthy

- `list()`: Converts to a list.

  - Example: `list_value = list("hello")` # Converts string "hello" to list ['h', 'e', 'l', 'l', 'o']

- `tuple()`: Converts to a tuple.

  - Example: `tuple_value = tuple([1, 2, 3])` # Converts list [1, 2, 3] to tuple (1, 2, 3)

- `set()`: Converts to a set.
  - Example: `set_value = set([1, 2, 2, 3])` # Converts list [1, 2, 2, 3] to set {1, 2, 3}
