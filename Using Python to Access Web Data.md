# Regular Expressions
- re.search() = see if string matches with reg exp like find()
- wild-card characters e.g. ^x*: - X-sieve:, X-DSPAM-Result:
- . = any characters, * = 0 or more
- ^X-\S+: 

```
# re.search() = find()

hand = open('file.txt')
for line in hand:
	line = line.rstrip()
	if line.find('From:') >= 0:
		print(line)
# re.search()
import re
hand = open('file.txt')
for line in hand:
	line = line.rstrip()
	if re.search('From:',line):
		print(line)
    
# re.search() like startswith()
if re.search('^From:',line) :

```

# Extracting Data
- [0-9]+ = one or more digits
- \$ = refer to real dollar sign
- non-greedy = matches as few chars as possible
- greedy = matches as longest possible string

^	Matches the beginning of a line
$	Matches the end of the line
.	Matches any character
\s	Matches whitespace
\S	Matches any non-whitespace character
*	Repeats a character zero or more times
*?	Repeats a character zero or more times (non-greedy)
+	Repeats a character one or more times
+?	Repeats a character one or more times (non-greedy)
[aeiou]	Matches a single character in the listed set
[^XYZ]	Matches a single character not in the listed set
[a-z0-9]	The set of characters can include a range
(	Indicates where string extraction is to start
)	Indicates where string extraction is to end



```

# Week 2 Assignment
```
import re

# open file
file = open("Using Python to acess web_wk2_assignment_actual.txt")

# filter only number as list
lst=list()
for line in file:
	line = line.rstrip()
	number = re.findall('([0-9]+)',line)
	lst = lst+number
print(lst)

# count number of values
count=0
for x in lst:
	count = count + 1
print(count)

# sum values
total=0
for value in lst:
    total = total + int(value)

print(total)
```

# Networked Technology
- Transport contro; protocol (TCP) 

# Assignment Week 3

You are to retrieve the following document using the HTTP protocol in a way that you can examine the HTTP Response headers.

```
import socket

mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect(('data.pr4e.org', 80))
cmd = 'GET http://data.pr4e.org/intro-short.txt HTTP/1.0\r\n\r\n'.encode()
mysock.send(cmd)

while True:
    data = mysock.recv(512)
    if len(data) < 1:
        break
    print(data.decode(),end='')

mysock.close()
```

# Assignment Week 4 - 1

```
from urllib import request
from bs4 import BeautifulSoup
html=request.urlopen('http://py4e-data.dr-chuck.net/comments_1240426.html').read()
soup = BeautifulSoup(html)
tags=soup('span')
sum=0
for tag in tags:
    sum=sum+int(tag.contents[0])
print(sum)
```








