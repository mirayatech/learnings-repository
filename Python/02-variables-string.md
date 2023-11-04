## Variables

- Variables are used to store values. They always ahve to be assigned otherwise we cant use them later

```Python
x = 5

x * 3 = 15

print(x) # 5
```

### They can be assigned to other variables

```Python
x = 5
y = x
print(y) # 5
```

### Reassigned at any time

```Python
x = 5
print(x) # 5
x = 10
print(x) # 10
```

### Assigned at the same time as other variables

```Python
x, y = 5, 10
print(x) # 5
print(y) # 10
```

## Naming

- Variables must start with a letter or underscore

  - `_cats` ✅
  - `2cats` ❌

- Rest of the name must consist of letters, number or underscores

  - `cats2` ✅
  - `cats$you@` ❌

- Names are case sensitive
  - `cats` and `Cats` are different variables

## Naming Conventions (most variables)

- snake case

  - `cats_are_cool`

- most variables should be lowercase

- `CAPITAL_SNAKE_CASE`: usually refers to constants

- UpperCamelCase: usually refers to a class

- variables that start and end with two underscores: `__no_touchy__` are supposde to be private or left alone

## String Concatination

- we can use `+` to combine strings
- we can use `*` to repeat strings

```Python
name = "John"
print("Hello " + name) # Hello John
print(name * 3) # JohnJohnJohn
```

- `8` + `"hello"` will give us an error, because we cant add a number to a string

### We can also use operators for concatenation

```Python
x = 10
formatted = f"I've told you {x} times already!"
or
formatted = "I've told you {} times already!".format(10)
```

## Interpolation

- we can use f-strings to interpolate variables into strings

```Python
name = "John"
print(f"Hello {name}") # Hello John
```

## Strings & Indexes (Indecies)

## Notice

- we should always be consistent, either `"''"` or `"''"` or `"he said \ "hello\" to me" `

- we can use qupute inside of qoutes as long as they are different
