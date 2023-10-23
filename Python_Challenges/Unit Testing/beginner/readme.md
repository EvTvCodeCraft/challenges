### 1. Arithmetic Operations

**Example:** Testing a simple addition function.

```python
def add(a, b):
    return a + b

# Unit Test
def test_add():
    assert add(2, 3) == 5
    assert add(0, 0) == 0
    assert add(-1, 1) == 0

test_add()
```

### 2. String Manipulation

**Example:** Testing a function that concatenates two strings.

```python
def concatenate_strings(str1, str2):
    return str1 + str2

# Unit Test
def test_concatenate_strings():
    assert concatenate_strings("Hello, ", "World!") == "Hello, World!"
    assert concatenate_strings("Python ", "Rocks!") == "Python Rocks!"

test_concatenate_strings()
```

### 3. List/Array Operations

**Example:** Testing a function that appends an element to a list.

```python
def append_to_list(lst, element):
    lst.append(element)
    return lst

# Unit Test
def test_append_to_list():
    my_list = [1, 2, 3]
    assert append_to_list(my_list, 4) == [1, 2, 3, 4]
    assert append_to_list([], "New Element") == ["New Element"]

test_append_to_list()
```

### 4. Conditional Statements

**Example:** Testing a function that checks if a number is positive.

```python
def is_positive(num):
    if num > 0:
        return True
    else:
        return False

# Unit Test
def test_is_positive():
    assert is_positive(5) == True
    assert is_positive(0) == False
    assert is_positive(-3) == False

test_is_positive()
```

### 5. Exception Handling

**Example:** Testing a function that raises an exception for division by zero.

```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Cannot divide by zero.")
    return a / b

# Unit Test
def test_divide():
    assert divide(10, 2) == 5.0
    try:
        divide(5, 0)
    except ZeroDivisionError as e:
        assert str(e) == "Cannot divide by zero."

test_divide()
```

These examples demonstrate how to create simple unit tests for basic functions in Python. The code for each function is followed by a unit test function that uses assertions to validate the expected outcomes.