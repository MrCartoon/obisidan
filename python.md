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
### Operations
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
### Functions
```python
def functionName(args,namedArg=)
	return args
```
### Classes (basic)
![[python#Syntax]]

### Files
```python
file = open(r"C:\ProgramFIles\receipt.csv") # windows
receipt = file.read()
file.close()
file2 = open(r"C:\ProgramFIles\receipt2.csv", 'w')
file2.write(receipt)
file2.close()

file3 = open('/home/ubuntu/Downloads/1.txt', 'a') # linux
file2.writeLInes('add to the end of the file')
file3.close()
file4 = open('./file.txt')
file4.read()
file4.close()

import os  
os.remove("demofile.txt")
```
## 2
### Git
https://learngitbranching.js.org/
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
## 3
### OOP
![[python#Syntax]]
### Simplest patterns
### OOP patterns: DRY, KISS, SOLID

## 4
### Regexp
```python
str = '''23409384023 | 348734 | Product
23409384023 | 423423 | Producttest'''


MYREG = re.compile(r'(23409384023 \| (\d+) \| Product)+')
print(re.findall(MYREG, str))

EMAIL_REGEXP = '''(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9]))\.){3}(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9])|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])'''
```
![email regexp diagram](https://i.stack.imgur.com/YI6KR.png)
### Exception handling (try -> catch)
```python
a = None
try:
  a = 1/0
  raise Exception("Facebook said 400")
except ZeroDivisionError as error:
  print(error)
except TypeError as error:
  print(error)
  a = 0/1
except (Error1, Error2):
  # testcode
  print('Error1 or Erro2')
except:
  print('all exceptions')
finally:
  print('run this anyway')
print(a)
```
### Modules
### Generators?
### Multithreading
```python
import threading
import random
import time

def methodA(text, result):
  time.sleep(random.random())
  result.append(text)

result = []

threadA = threading.Thread(target=methodA,args=('A', result,))
threadB = threading.Thread(target=methodA,args=('B', result,))
threadB.start()
threadA.start()

threadA.join()
threadB.join()
print(result)
```
### GIL?
### Virtualenv +-?
### PEP8 codestyle
### unit test
```python
import unittest


class MyArray:

  def __init__(self, arr):
    self.array = arr

  def size(self):
    return len(self.array)

  def sum(self):
    return sum(self.array)


class TestMyArray(unittest.TestCase):

  def setUp(self):
    self.arr1 = [1, 3, 2]
    self.arr2 = [3, 7, 3, 4]
    self.arr3 = [200, 10, 1]

  def test1(self):
    self.assertEqual(MyArray(self.arr1).size(), 3)
    self.assertEqual(MyArray(self.arr2).size(), 4)
    self.assertEqual(MyArray(self.arr3).size(), 3)

  def test2(self):
    self.assertEqual(MyArray(self.arr1).sum(), 6)
    self.assertEqual(MyArray(self.arr2).sum(), 17)
    self.assertEqual(MyArray(self.arr3).sum(), 211)


unittest.main()
```
### py.test
```python
import pytest

class MyArray:

  def __init__(self, arr):
    self.array = arr

  def size(self):
    return len(self.array)

  def sum(self):
    return sum(self.array)

@pytest.fixture
def setup_variables():
  return [1, 3, 2], [3, 7, 3, 4], [200, 10, 1]

def test_size(setup_variables):
  arr1, arr2, arr3 = setup_variables
  assert MyArray(arr1).size() == 3
  assert MyArray(arr2).size() == 4
  assert MyArray(arr3).size() == 3

def test_sum(setup_variables):
  arr1, arr2, arr3 = setup_variables
  assert MyArray(arr1).sum() == 6
  assert MyArray(arr2).sum() == 17
  assert MyArray(arr3).sum() == 211
```
## 5
### Scrapping: basic requests, scrapy
```bash
pip install scrapy
scrapy startproject ragul
cd ragul
scrapy genspider church https://godsglory.church/
```
`ragul/items.php`
```python
+++

class InstItem(scrapy.Item):
    username = scrapy.Field()
    url = scrapy.Field()
```
`ragul/spiders/church.py`
```python
+++

from ragul.items import InstItem

class ChurchSpider(scrapy.Spider):
    name = "church"
    allowed_domains = ["godsglory.church"]
    start_urls = ["https://godsglory.church/"]

    def parse(self, response):
        for link in response.css('.sidebar-block.typography a'):
            item = InstItem()
            item['username'] = link.css('::text').get()
            item['url'] = link.css('::attr(href)').get()
            yield item
```
`ragul/settings.py`
```python
+++

FEED_FORMAT = 'json'
FEED_URI = 'output.json'
```

```bash
scrapy crawl church
```
Вивід `output.json`
```json
[
{"username": "@gods_glory_church_if", "url": "https://www.instagram.com/gods_glory_church_if/"},
{"username": "@glory.church.lv", "url": "https://www.instagram.com/glory.church.lv/"},
{"username": "@gloryckorg", "url": "https://www.instagram.com/gloryckorg/"}
]
```
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
        # TODO

    def min(self):
        # TODO

    def desc(self):
        # TODO

    def asc(self):
        # TODO

    def odd(self):
        #TODO

    def multiple_to_three(self):
        # TODO

    def uniq(self):
        # TODO

    def divide_on_ten(self):
        # TODO

    def chars(self):
        # TODO

    def switch(self):
        # TODO

    def before_min(self):
        # TODO

    def three_smallest(self):
        # TODO
```
