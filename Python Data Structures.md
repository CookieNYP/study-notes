# Strings
- index value starts at zero e.g. string = banana, index = 0(b),1(a),2(n),3(a),4(n),5(a)


```
 # looping through strings

fruit = 'banana'
index = 0
while index < len(fruit) : 
	letter = fruit[index]
	print(index, letter)
	index = index + 1
  
# Slicing Strings
s = 'Monty Python'
print(s[0:4]) # get string index 0-3
print(s[8:20]) # get string index 8-19

```

# Manipulating Strings
- lower()
- dir() 
- string library = e.g. capitalize

```
# Using in as a logical operator

fruit = 'banana'
'n' in fruit # >> True
'm' in fruit # >> False

# Searching a string

fruit = 'banana'
pos = fruit.find('na')
print(pos)

# search and replace

greet = 'hello nike'
x = greet.replace('nike', 'adidas')
print(x)

# stripping whitespace
str.lstrip() # left
str.rstrip() # right
str.strip() # both sides


```
