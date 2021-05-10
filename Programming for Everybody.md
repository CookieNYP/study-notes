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

# Files
- files stored in second memory
- file handle = connect to file's data
- open() = then we can choose to read or write data
- input() = prompt user for a file name to open
- e.g. text file, csv, excel
- \n = new line
- print statement adds a newline to each line and each line has a new line at the end
- bad file name = use try/except

```
# print each line in a file

xfile = open('xxx.txt')
for cheese in xfile
	print(xfile)

# print only line that start with 'From: ' 
file.startswith('From: ')

# remove new line at the end of a line
 line = line.rstrip()
 
 
 
	
```

# Assignment 7.1 : Print line in a file with uppercase
```
# Use words.txt as the file name
fname = input("Enter file name: ")

try :
	fh = open(fname)
except :
	print('Cannot find a file')
	quit()

for line in fh :
	line = line.upper()
	line = line.rstrip()
	print(line)
```

# Lists

- list = collection, >1 values in a variable
- BTS = ['RM','Jin','Suga','J-Hope','Jimin','V','JK']
- index starts with 0

```
# index starts with 0
BTS = ['RM','Jin','Suga','J-Hope','Jimin','V','JK']
print(BTS[0])
# >>> RM

# len = count the variable in a list
BTS = ['RM','Jin','Suga','J-Hope','Jimin','V','JK']
print(len(BTS))
# >>> 7

# range
print(range(len(BTS)))
# >>> range(0,7)

x = list(range(5))
print(x)
# >>> [0, 1, 2, 3, 4]

```

# 8.2 Manipulating Lists



```
BTS = ['RM','Jin','Suga','J-Hope','Jimin','V','JK']

# sliced
print(BTS[3:5])

# build a list from scratch
One_Piece = list()
One_Piece.append('Luffy')
print(One_Piece)
# >>> ['Luffy']
One_Piece.append('Zolo')
print(One_Piece)
# >>> ['Luffy', 'Zolo']


# lists are in order

BTS.sort()
print(BTS)
# >>> ['J-Hope', 'JK', 'Jimin', 'Jin', 'RM', 'Suga', 'V']


# build a list from loop
One_Piece = list()
while True :
	member = input('Enter a member name:')
	if member == 'done' : break
	One_Piece.append(member)
```

# Lists and Strings

```
# split string by space
lyrics = 'Forever         we are young'
new = lyrics.split()
print(new)
# >>>  ['Forever', 'we', 'are', 'young']


# split string by other symbol
lyrics = 'So.show.me.I.show.you'
new = lyrics.split('.')
print(new)
# >>>  ['So', 'show', 'me', 'I', 'show', 'you']
```

# Assignment 8.4
```
# open file -> read line by line -> split in to words into list -> sort -> print ASC

fname = input("Enter file name: ")
try :
	fh = open(fname)
except :
	print('Cannot open a file')

lst = list()
for line in fh:
	word = line.rstrip().split()
	for value in word:
		if value in lst :
			continue
		else :
			lst.append(value)
lst.sort()
print(lst)
```

# Assignment 8.5

```
fname = input("Enter file name: ")
if len(fname) < 1 : fname = "mbox-short.txt"

fhand = open("mbox-short.txt")
count = 0
for line in fhand:
    line = line.rstrip()
    if line == "": continue
        
    words = line.split()
    if words[0] !="From": continue
        
    print(words[1])
    count = count+1

print ("There were", count, "lines in the file with From as the first word")
```

# Dictionaries
- collection as list
- list is order collection []
- dict = associative arryas
- dictionary = more mess, not stay in order but more powerful because key:value {}
- [list] vs {dict}
- dict = {'leader': 'RM'} >> leader = key, RM = value
- keys()
- values()
- items() = give a list of both keys and values

```
BTS = dict()
BTS['leader'] = 'RM'
BTS['swag & sweet'] = 'Suga'
BTS['dancing machine'] = 'J-Hope'
BTS['WWH'] = 'Jin'
BTS['angel'] = 'Jimin'
BTS['good boy'] = 'V'
BTS['golden maknae'] = 'JK'

print(BTS)
# >>> {'leader': 'RM', 'swag & sweet': 'Suga', 'dancing machine': 'J-Hope', 'WWH': 'Jin', 'angel': 'Jimin', 'good boy': 'V', 'golden maknae': 'JK'}

print(BTS['WWH'])
# >>> Jin

print(BTS.values())
# >>> dict_values(['RM', 'Suga', 'J-Hope', 'Jin', 'Jimin', 'V', 'JK'])

```

# Counting with dictionaries
- counts.get(keys, 0) = 0 is default value in case key is not found

```
# count value in dictionaries

counts = dict()
BTS = ['RM','Jin','Suga','J-Hope','Jimin','V','JK','JK','V','V','RM']
for member in BTS :
	if member not in counts :
		counts[member] = 1
	else :
		counts[member] = counts[member] + 1
print(counts)
# >>> {'RM': 2, 'Jin': 1, 'Suga': 1, 'J-Hope': 1, 'Jimin': 1, 'V': 3, 'JK': 2}

# simplify count
counts = dict()
BTS = ['RM','Jin','Suga','J-Hope','Jimin','V','JK','JK','V','V','RM']
for member in BTS :
	counts[member] = counts.get(member, 0) + 1
print(counts)

# find most common words

counts = dict()
print('Enter a line of text:')
line = input('')

words = line.split()

print('words:', words)

print('Counting...')
for word in words:
	counts[word] = counts.get(word,0) + 1
print('counts', counts)

# find most common words

lyrics = "Cause I I I m in the stars tonight So watch me bring the fire and set the night alight (hey) Shining through the city with a little funk and soul So I ma light it up like dynamite, whoa oh oh"

counts = dict()
line = lyrics
words = line.split()
print('words:', words)
print('Counting...')
for word in words:
	counts[word] = counts.get(word,0) + 1
print('counts', counts)

```



