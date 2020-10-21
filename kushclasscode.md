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


### To be continued...