# Problems


### Stack memory model
```python
class Stack(object):
    def __init__(self, size=8):
        self.contains = [0 * x for x in range(size)]

# All operands (numbers in the stack) are LESS THAN OR EQUAL TO 255
# All operands are of type 'int'
# Functions to have:
#   * push
#   * pop
#   * add
#   * sub

# Note: To check type of variable, use function isinstance(variable, type)
```