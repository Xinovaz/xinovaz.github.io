# In-class code!


Guessing game:
```python
from random import randint

while True:
  number = randint(1, 10)
  guess = input('Guess the number: ')
  if int(guess) == number:
    print('Well done!')
  else:
    print('Try again.')
  ```

File I/O example
```python
cmd = input('>>> ')

if cmd == 'read':
  with open('cool.txt', 'r+') as f:
    text = f.readlines()
    for line in text:
      if 'NAME:' in line:
        print(line.strip('NAME:'))
      if 'DOB:' in line:
        print(line.strip('DOB:'))
else:
  name = cmd.split(' ')[1]
  dob = cmd.split(' ')[2]
  fname = cmd.split(' ')[0]
  with open(f'{fname}.txt', 'w+') as f:
    f.write('NAME: ' + name)
    f.write('DOB: ' + dob)
```

Objects and Inheritance
```python
class Car(object):
  def __init__(self, maker, model, hp):
    self.maker = maker
    self.model = model
    self.hp = hp
  def maximum_speed(self):
    first = 2 * self.hp
    second = 1.225 * 0.25 * 8
    speed = (first/second)**(1/3)
    return speed

class Sports_Car(Car):
  def __init__(self, maker, model, hp):
    super().__init__(maker, model, hp)
  def rev(self):
    print("Vroom! Vrooooom!")
    
lambo = Sports_Car("lamborghini", "aventador", 729)

lambo.rev()

print(lambo.maximum_speed())
```

Job Scraper
```python
import requests
from bs4 import BeautifulSoup

URL = "https://stackoverflow.com/jobs"
page = requests.get(URL)

soup = BeautifulSoup(page.content, 'html.parser')

listings = soup.find_all('div', class_=lambda cl: cl is not None and '-job' in cl)

jobs = []
for listing in listings:
  job = listing.find('span')
  name = job.text
  name = name.strip()
  jobs.append(name)

jobs = set(jobs)

for j in sorted(jobs):
  if j != 'featured':
    print(j)
```


### To be continued...