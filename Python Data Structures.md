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

# Tuples ()
- list that immutable, cannot change 
- suggest to use it for temporary variable
- d.items() = list of tuples in dictionary


```
(x,y) = (4,'fred')
print(y)

# Tuples are comparable

x = (41,1,2) < (5,-1,4)
print(x)
# >>> True , it checks the first pair (0 < 5) only

# sorting

d = {'c':8,'b':9,'a':1}
print(sorted(d.items()))
# >>> [('a', 1), ('b', 9), ('c', 8)]


# sort by values

tmp = list()
for k,v in d.items() :
	tmp.append((v,k))
print(tmp)
tmp = sorted(tmp, reverse =True)
print(tmp)
# >>> [(9, 'b'), (8, 'c'), (1, 'a')]

```

# Assignment 10.2

 Write a program to read through the mbox-short.txt and figure out the distribution by hour of the day for each of the messages. You can pull the hour out from the 'From ' line by finding the time and then splitting the string a second time using a colon.
From stephen.marquard@uct.ac.za Sat Jan  5 09:14:16 2008
Once you have accumulated the counts for each hour, print out the counts, sorted by hour as shown below.

```
name = input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
d=dict()
for line in handle:
    if not line.startswith("From "): 
        continue
    else:    
        line=line.split()
        line=line[5]
        line=line[0:2]
        d[line]=d.get(line,0)+1

lst=list()        
for value,count in d.items():
    lst.append((value,count))

lst.sort()
for value,count in lst:
    print (value,count)
```


