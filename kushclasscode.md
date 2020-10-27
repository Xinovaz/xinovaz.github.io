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

### To be continued...