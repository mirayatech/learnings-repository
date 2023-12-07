# Dictionary Comprehension 🧠

- Dictionary comprehension is a concise way to create new dictionaries from existing ones. 🔄

## Basic Example 🌟

- Transforming one dictionary into another with operations on the key-value pairs.

```python
numbers = dict(first=1, second=2, third=3)
squared_numbers = {key: value ** 2 for key, value in numbers.items()}

# Output: {'first': 1, 'second': 4, 'third': 9}
```

## Squaring Numbers 🔢

- Creating a dictionary with numbers as keys and their squares as values.

```python
squared = {num: num ** 2 for num in [1, 2, 3, 4, 5]}

# Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

## Upper Case Transformation 📢

- Converting all keys and values in a dictionary to upper case.

```python
person = {
    "name": "Bob",
    "job": "Developer",
    "country": "Norway"
}

yelling = {key.upper(): value.upper() for key, value in person.items()}

# Output: {'NAME': 'BOB', 'JOB': 'DEVELOPER', 'COUNTRY': 'NORWAY'}
```
