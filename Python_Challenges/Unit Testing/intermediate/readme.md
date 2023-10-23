# Intermediate-Level Unit Testing Examples

The following examples are for intermediate-level unit testing. These examples cover a range of scenarios and functions that are more complex than the basic-level examples.

### 6. Functions and Methods

**Example:** Testing a function that calculates the area of a rectangle.

```python
def calculate_rectangle_area(length, width):
    return length * width

# Unit Test
def test_calculate_rectangle_area():
    assert calculate_rectangle_area(4, 6) == 24
    assert calculate_rectangle_area(0, 10) == 0
    assert calculate_rectangle_area(3, 3) == 9

test_calculate_rectangle_area()
```

### 7. Data Structures

**Example:** Testing a function that implements a stack.

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        return self.items.pop()

    def is_empty(self):
        return len(self.items) == 0

# Unit Test
def test_stack():
    stack = Stack()
    stack.push(1)
    stack.push(2)
    stack.push(3

    assert stack.pop() == 3
    assert stack.is_empty() == False
    assert stack.pop() == 2
    assert stack.pop() == 1
    assert stack.is_empty() == True

test_stack()
```

### 8. File I/O

**Example:** Testing a function that reads data from a file.

```python
def read_file_content(file_path):
    try:
        with open(file_path, 'r') as file:
            content = file.read()
        return content
    except FileNotFoundError:
        return None

# Unit Test
def test_read_file_content():
    content = read_file_content("sample.txt")
    assert content == "This is a sample file content."

    non_existent_content = read_file_content("non_existent.txt")
    assert non_existent_content is None

test_read_file_content()
```

### 9. API Calls

**Example:** Testing a function that makes a simple API call.

```python
import requests

def get_json_response(url):
    response = requests.get(url)
    if response.status_code == 200:
        return response.json()
    return None

# Unit Test
def test_get_json_response():
    url = "https://jsonplaceholder.typicode.com/posts/1"
    response_data = get_json_response(url)
    assert response_data is not None
    assert 'title' in response_data
    assert 'body' in response_data

test_get_json_response()
```

### 10. Regular Expressions

**Example:** Testing a function that extracts email addresses from a text.

```python
import re

def extract_emails(text):
    pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,7}\b'
    return re.findall(pattern, text)

# Unit Test
def test_extract_emails():
    text = "Contact us at support@example.com or info@company.net"
    emails = extract_emails(text)
    assert emails == ['support@example.com', 'info@company.net']

test_extract_emails()
```

These intermediate-level unit testing examples cover more complex functions and scenarios. Each example includes a function to be tested and a unit test function to validate its behavior. You can use these examples as a foundation and expand your unit testing skills to cover a wider range of scenarios and code.