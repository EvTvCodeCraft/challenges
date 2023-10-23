# Advanced-Level Unit Testing Examples

The following examples are for advanced-level unit testing. These examples cover more complex scenarios, including object-oriented programming, concurrency, database interaction, web services, and dependency injection.

### 11. Object-Oriented Programming

**Example:** Testing an object-oriented class that represents a bank account.

```python
class BankAccount:
    def __init__(self, account_id, balance=0):
        self.account_id = account_id
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
        else:
            raise ValueError("Insufficient funds")

# Unit Test
def test_bank_account():
    account = BankAccount(account_id="12345", balance=1000)
    account.deposit(500)
    assert account.balance == 1500
    account.withdraw(200)
    assert account.balance == 1300

test_bank_account()
```

### 12. Concurrency and Parallelism

**Example:** Testing a function that uses multi-threading to perform concurrent tasks.

```python
import threading

def increment_counter(counter, n):
    for _ in range(n):
        counter.value += 1

# Unit Test
def test_concurrent_increment():
    counter = threading.local()
    counter.value = 0

    thread1 = threading.Thread(target=increment_counter, args=(counter, 1000))
    thread2 = threading.Thread(target=increment_counter, args=(counter, 1000))

    thread1.start()
    thread2 start()

    thread1.join()
    thread2.join()

    assert counter.value == 2000

test_concurrent_increment()
```

### 13. Database Interaction

**Example:** Testing a function that performs CRUD operations on a SQLite database.

```python
import sqlite3

def create_table():
    connection = sqlite3.connect("my_database.db")
    cursor = connection.cursor()
    cursor.execute("CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT)")
    connection.commit()
    connection.close()

def insert_user(name):
    connection = sqlite3.connect("my_database.db")
    cursor = connection.cursor()
    cursor.execute("INSERT INTO users (name) VALUES (?)", (name,))
    connection.commit()
    connection.close()

def retrieve_users():
    connection = sqlite3.connect("my_database.db")
    cursor = connection.cursor()
    cursor.execute("SELECT name FROM users")
    users = [row[0] for row in cursor.fetchall()]
    connection.close()
    return users

# Unit Test
def test_database_interaction():
    create_table()
    insert_user("Alice")
    insert_user("Bob")
    users = retrieve_users()
    assert "Alice" in users
    assert "Bob" in users

test_database_interaction()
```

### 14. Web Services

**Example:** Testing a function that interacts with a RESTful API.

```python
import requests

def get_github_user(username):
    url = f"https://api.github.com/users/{username}"
    response = requests.get(url)
    if response.status_code == 200:
        return response.json()
    return None

# Unit Test
def test_get_github_user():
    user = get_github_user("octocat")
    assert user is not None
    assert 'login' in user
    assert 'name' in user

test_get_github_user()
```

### 15. Dependency Injection

**Example:** Testing a function with dependency injection using mock objects.

```python
from unittest.mock import Mock

class EmailService:
    def send_email(self, to, subject, message):
        # Code to send an email
        pass

def send_notification(email_service, user_id, message):
    email_service.send_email(user_id, "Notification", message)

# Unit Test
def test_send_notification():
    email_service = Mock(spec=EmailService)
    send_notification(email_service, "user@example.com", "Hello, World!")
    email_service.send_email.assert_called_with("user@example.com", "Notification", "Hello, World!")

test_send_notification()
```

These advanced-level unit testing examples cover more complex scenarios, providing a function to be tested and a unit test function to validate its behavior. You can use these examples as a foundation for building advanced-level unit tests for your projects.