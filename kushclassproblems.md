# Problems


### Stack memory model
```python
class Stack(object):
	def __init__(self, size=8):
		self.contains = [0 * x for x in range(size)]

# All operands (numbers in the stack) are LESS THAN OR EQUAL TO 255
# All operands are of type 'int'
# Functions to have:
#	 * push
#	 * pop
#	 * add
#	 * sub

# Note: To check type of variable, use function isinstance(variable, type)
```
#### Solution:
```python
class StackException(Exception):
	pass

class Stack(object):
	def __init__(self, size=8):
		self.size = size
		self.contains = []
	
	def update(self):
		for index, operand in enumerate(self.contains):
			self.contains[index] = abs(operand)
		while len(self.contains) > self.size:
			self.contains.pop(-1)
			raise StackException("Stack Overflow Error")
	
	def push(self, value):
		if isinstance(value, int):
			if value <= 255 and value >= 0:
				self.contains.append(value)
				self.update()
			else:
				raise StackException("Integer Overflow Error")
		else:
			raise StackException("Invalid Data Error")

	def pop(self):
		if self.contains != []:
			top = self.contains[-1]
			self.contains.pop(-1)
			self.update()
			return top
		else:
			raise StackException("Illegal Pop Attempt Error")

	def add(self):
		rhs = self.pop()
		lhs = self.pop()
		self.push(lhs + rhs)
		self.update()

	def sub(self):
		rhs = self.pop()
		lhs = self.pop()
		self.push(lhs - rhs)
		self.update()

```