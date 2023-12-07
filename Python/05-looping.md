# Loops 🔄

- Loops are all about repeating a task over and over again. 🔄
- There are two types of loops in Python: `for` and `while`. 🤹‍♂️

## For Loops ⏭️

```python
# Example: Iterating over a range
for i in range(5):
    print(i)

# Output:
# 0
# 1
# 2
# 3
# 4

# Example: Iterating over a string
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

### Ranges 🔢

- `range()` returns a sequence of numbers.
- A **Range** is a slice of the number line.
- `range()` can take one to three arguments.

```python
# Example: range with one argument
for i in range(5):
    print(i)

# Example: range with two arguments
for i in range(1, 5):
    print(i)

# Example: range with three arguments
for i in range(1, 10, 2):
    print(i)
```

## While Loops ⏯️

- A `while` loop executes as long as a condition is `True`.

```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

## Break and Continue 🚦

- `break` exits loops, and `continue` skips the current iteration.

### Break ⏹️

- `break` exits a loop early.

```python
# Example: Exiting a while loop
while True:
    command = input("Type 'exit' to exit: ")
    if command == "exit":
        break

# Example: Exiting a for loop early
for x in range(1, 101):
    print(x)
    if x == 3:
        break
```

### Code Example 📝

```python
times = int(input("How many times do I have to tell you? "))

for time in range(times):
    print("CLEAN UP YOUR ROOM!")
    if time >= 3:
        print("Do you even listen anymore?")
        break
```
