# Loops

- Loops is all about repeating a task over and over again.
- There are two types of loops in Python:

  - `for` loop
  - `while` loop

## For Loops

```python
for i in range(5):
    print(i)

# Output:
# 0
# 1
# 2
# 3
# 4

for letter in "coffee":
    print(letter)

# Output:
# c
# o
# f
# f
# e
# e
```

### Ranges

- `range()` is a function that returns a sequence of numbers.
- A **Range** is just a slice of the number line.
- `range()` can take up to three arguments:

  - `range(stop)`
  - `range(start, stop)`
  - `range(start, stop, step)`

```python
# range(stop)
for i in range(5):
    print(i)

# Output:
# 0
# 1
# 2
# 3
# 4
```

```python
# range(start, stop)
for i in range(1, 5):
    print(i)

# Output:
# 1
# 2
# 3
# 4
```

```python
# range(start, stop, step)
for i in range(1, 10, 2):
    print(i)

# Output:
# 1
# 3
# 5
# 7
# 9
```

## While Loops

- A `while` loop will keep executing as long as a condition is `True`.

```python

i = 1
while i <= 5:
    print(i)
    i += 1

```

## Break and Continue

- `break` and `continue` are two special keywords that can be used inside loops.

### Break

- it gives us the ability to exit out of while loops whenever we want.

```python
while True:
    command = input("Type 'exit' to exit: ")
    if (command == "exit"):
        break
```

- We can also use it to end `for` loops early.

```python
for x in range(1, 101):
    print(x)
    if x == 3:
        break
```

### cod example

```python
times = int(input("How many times do I have to tell you? "))

for time in range(times):
    print("CLEAN UP YOUR ROOM!")
    if time >= 3:
        print("Do you even listen anymore?")
        break
```
