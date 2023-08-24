#coding
https://geekhub.ck.ua/

[[GeekHub S13 python description]]

## 1
### Syntax
```python
snake_case = ""
SNAKE_CASE = ""
camelCase = ""
PascalCase = ""

class User:
  def __init__(self, name, age, email):
    self.name = name
    self.age = age
    self.email = email

  def info(self):
    return '(' + self.email + ') ' + self.name + ' ' + self.age

  def resetPassword(self, newPassword):
    self.password = newPassword
    

user1 = User("Dania", '', '')
user2 = User("Sviat", "22", "test@sviat.me")

user1.legs = 1

class Animal:
  def __init__(self, name):
    self.nickname = name

  def name(self):
    return self.nickname

class Dog(Animal): {}

dog = Dog("dog name")

print(dog.name())
```
### Datatypes
```python
int
1,2,3

float
1.1,1.2

str
""
''

bool
True
False
None

complex

bytes

list
["Banana", "Apple", "Grape"]

dict
{"name" : "John", "age" : 36, "children" : []}

range
range(6) #=> range(0, 6)
```
### Operations?
### Functions
### Classes (basic)
### Files

## 2
### Git

## 3
### OOP
### Simplest patterns
### OOP patterns: DRY, KISS, SOLID

## 4
### Regexp
### Exception handling (try -> catch)
### Modules
### Generators?
### Multithreading
### GIL?
### Virtualenv +-?
### PEP8 codestyle
### unit test
### py.test

## 5
### Scrapping: basic requests, scrappy