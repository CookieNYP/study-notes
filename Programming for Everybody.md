# Programming for Everybody

Introduction
- for those with no prior programming experience
- focus on the core concepts of programming
- materials: https://www.py4e.com/
- free ebook: https://www.py4e.com/book
- sample code: https://www.py4e.com/materials

# Why Program
- be technology maker, not just consumer
- syntax error = i don't know what to do

# Hardware Overview
- Input & Output devices
- CPU = who keep asking what's next
- Main Memory = answering the question to CPU
- Secondary Memory (Hard drive, USB) = this is where we write Python

# Python as a Language
- Python is powerful and enjoyable langauge

# Writing Paragraphs of Code
- RESERVED WORD = e.g. if, print, assert, for...
- python file = file.py
- script
- chevron prompt = >>>

file reading pattern
- sequential steps =
- conditional steps = if...else
- repeated steps = while

# Expressions
- constants = fixed values like numbers, letters
- variables = case sensitive, should be mnemonic (easy to understand for human)
- reserved words
- sentences/lines
- numeric expressions = +, -, *, /, **, % (remainder)
- type = string, integer
- integer division = return as a floating point result
- comments in python = # comments
- 

```
type(xx) # str
type(1) # int
type(98.9) # float

# type conversions
print(float(99 + 100)) # 199.0

# string conversion
x = '123'
y = int(x)
print(y + 1) # 124

# user input
nam = input('Who are you')
print('Welcome', nam)

```

# Conditional Statements

- if statements
- comparison operators = <, >, == (equal to), !=
- = is used for assignment
- if...elif...else = run only one statement
- try...except = alternative for code in case it doesn't work

```
# Example
x  = 100
if x < 10:
	print('Smaller')
if x > 20:
	print('Bigger')
print('Finis')

# try/except
astr = 'Hello Bob'
try:
	istr = int(astr) #if thing works out, do this
except:
	istr = -1 # if thing didn't work out, do this

print('First', istr)

```

# Using Functions
- function is where stored and reused
- def keywords = defines the function but doesn't execute/run the code. Just remember the code
- def will run the code until we invoke it: reuse -> call -> invoke
- def = arguments, parameters and results
```
# type conversions

type(i)
float(i)
int(i)

# def
# max = function
# inp = parameter
# return = result
def max(inp):
	blah
	blah
	for x in inp:
		blah
		blah
	return 'w'

# Hello World is argument
big = max('Hello World')
print(big)

# multiple parameters
def max(a, b)

# example def
def stuff():
    print('Hello')
    return
    print('World')

stuff()
>>> Hello

```

# Assignment 4.6

```
def computepay(h,r):
    if h <= 40:
    	return h*r
    if h > 40:
    	return ((h-40)*1.5*r)+(40*r)


hrs = 45
h = float(hrs)

rate = 10.50
r = float(rate)

p = computepay(h,r)
print("Pay",p)
```

# Loops and Iteration
- do repetitive tasks
- infinite loop = will run until the battery run out!
- break statements = ends the current loop
- continue = ent the current iteation and jumps to the top of the loop and starts the next iteration
- definite loops = finite loop, use for...in... for list, file

```

# infinite loop

n = 5
while n > 0 :
	print (n)

# repeated steps

n = 5
while n > 0 :
	print (n)
	n = n - 1 # iteration variable to control infinite loop

# definite loop

for i in [5,4,3,2,1] :
	print(i)
print('Blastoff!')

# definite loop 2

friends = ['a','b','c']
for friend in friends :
	print('Happy New Year', friend)
print('End')

```

# Finding the largest value

```
largest_so_far = -1
print('Before' , largest_so_far)
for num in [9,21,12,3,74,13] :
	if num > largest_so_far :
		largest_so_far = num
	print(largest_so_far, num)
print('After' , largest_so_far)
```

# Loop Idioms
- continue a loop
- summing in a loop
- finding average in a loop
- filtering in a loop
- search using a boolean variable
- find the smallest value
```
# None is flag value
largest_so_far = None
print('Before' , largest_so_far)
for num in [9,21,12,3,74,13] :
	if largest_so_far is None :
		largest_so_far = num #Prime getting started
	elif num > largest_so_far :
		largest_so_far = num
	print(largest_so_far, num)
print('After' , largest_so_far)

```

# Assignment 5.2

```
largest = None 
smallest = None 
while True: 
  num = input("Enter a number: ") 
  if num == "done" : 
    break 
  try: 
    num1 = int(num) 
  except: 
    print("Invalid input") 
    continue 
  if largest is None or num1 > largest:
    largest = num1 
  if smallest is None or num1 < smallest:
    smallest = num1 

print("Maximum is", largest) 
print("Minimum is", smallest)
```
