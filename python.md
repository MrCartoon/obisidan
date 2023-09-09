#coding

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

## HW1
### В класі ’Lesson1’
- Реалізувати метод `(sum)` для підрахування суми з всіх цифр вхідного параметру.
- В методі `age` розрахувати скільки вам років і повернути `String` у наступному формат: `Я живу 23 років, або 8721 днів, або 209320 годин, або 12559226 хвилин, або 753553635 секунд`
- Реалізувати метод `(name)` який буде зчитувати ПІБ з клавіатури та повертити `String` у форматі: `Hello Alex Super Man!`
```python
class Lesson1:
    def sum(self, val):
        # TODO

    def age(self, birthday):
        # TODO

    def name():
        # TODO
```

### В класі `MyArray` реалізувати наступне:
- ~~Конструктор який приймає масив і зберігає його в змінну `(__init__)`~~
- Метод який повертає розмір масива
- Метод який повертає перевернутий масив
- Метод який повертає найбільший елемент масива
- Метод який повертає найменший елемент масива
- Відсортований по зростанню `(asc)`
- Відсортований по спаданню `(desc)`
- Метод який повертає лише непарні числа
- Метод який повертає лише числа кратні трьом
- Метод який повертає лише унікальні числа
- Метод який повертає масив елементи якого розділені на 10 зі знаком після коми
- Метод який повертає масив з символами алфавіту відповідно до індексу елементів масиву `(chars)`
- Метод який повертає масив у якому максимальний та мінімальний елементи поміняні місцями `(switch)`
- Метод який повертає масив, який містить елементи, що передують найменшому елементу
- Метод який повертає масив, який містить 3 найменші елементи
```python
class MyArray:
    def __init__(self, arr):
        self.array = arr

    def size(self):
        #TODO

    def reverse(self):
        # TODO

    def max(self):
        #TODO

    def min(self):
        # TODO

    def desc(self):
        #TODO

    def asc(self):
        # TODO

    def odd(self):
        #TODO

    def multiple_to_three(self):
        # TODO

    def uniq(self):
        #TODO

    def divide_on_ten(self):
        #TODO

    def chars(self):
        # TODO

    def switch(self):
        #TODO

    def before_min(self):
        # TODO

    def three_smallest(self):
        # TODO
```


# Logical operators
```python
var1 = True
var2 = False
var3 = False
var4 = True

var1 and (var2 or var3) and var4 #=> False
var1 and var2 or var3 and var4 #=> False
a = [1, 2]
b = [1, 2]

a is b #=> False

a == b #=> True
```

# Git

```bash
git status # подивись незбережені зміни
git add . # додати зміни в коміт
git commit -m 'меседж' # зберегти коміт (закомітити)
git push # запушити/завантажити в хмару (нинішню гілку)
git pull # скачати зміни з хмари (всі гілки)

git branch # вивести список гілок
git branch name # створити нову гілку під назвою name відколовшись від активної
git branch -D name # видалити гілку name
git merge name # змерджити name в активну гілку
```

### Regexp
```python
str = '''23409384023 | 348734 | Product
23409384023 | 423423 | Producttest'''


MYREG = re.compile(r'(23409384023 \| (\d+) \| Product)+')
print(re.findall(MYREG, str))

EMAIL_REGEXP = '''(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9]))\.){3}(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9])|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])'''
```