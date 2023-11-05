## 🌐 Conditional Statements

Conditional statements in Python allow you to execute different blocks of code depending on the condition.

```python
if 1 > 2:
    print("1 is greater than 2")
elif 2 > 1:
    print("2 is greater than 1")
else:
    print("1 is equal to 2")
```

## 📁 Nested Conditionals

Python supports nested conditional statements, which allows for more complex logic.

```python
if age != '':
    if age >= 18:
        print("You can enter, but need a wristband")
    elif age >= 21:
        print("You can enter and drink")
    else:
        print("You can't come in, little one! :(")
else:
    print("Please enter an age")
```

## ✨ Truthiness

In Python, the truthiness of a value can be checked to see if it's considered `True` or `False` in a boolean context.

```python
x = 1
print(x is 1)  # True
print(x is 0)  # False

print(bool("Hello"))  # True
print(bool(""))       # False
print(bool(" "))      # True
```

- Any non-empty string is "truthy," and an empty string is "falsy":
  - `bool("")` is `False`
  - `bool(" ")` is `True`

## 🔍 Comparison Operators

Python provides a lot of operators for comparing values:

- `==`: equal to
- `!=`: not equal to
- `>`: greater than
- `<`: less than
- `<=`: less than or equal to
- `>=`: greater than or equal to
- `is`: is the same object

```python
print(1 == 1)  # True
print(1 != 1)  # False
print(1 < 1)   # False
print(1 > 1)   # False
print(1 >= 1)  # True
print(1 <= 1)  # True
```

## 🤝 Logical Operators

Logical operators are used to combine conditional statements:

- `and`: both conditions must be true
- `or`: one of the conditions must be true
- `not`: negates the truth value

```python
print(1 < 2 and 2 < 3)  # True
print(1 < 2 and 2 > 3)  # False
print(1 < 2 or 2 > 3)   # True
```

## ↩️ Ternary Operator

The ternary operator in Python allows writing conditional statements in a single line.

```python
age = 22
message = "Eligible" if age >= 18 else "Not Eligible"
print(message)  # Eligible
```

## 🆚 is vs. "=="

The `is` operator compares the identity of two objects, while `==` compares their values.

```python
x = [1, 2, 3]
y = [1, 2, 3]
print(x == y)  # True
print(x is y)  # False

a = [1, 2]
clone = a
print(a is clone)  # True
```
