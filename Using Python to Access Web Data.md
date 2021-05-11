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

# Assignment Week 4 - 1 sum data in url

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

# Assignment Week 4-2 Finding name in url


```
from bs4 import BeautifulSoup
import urllib.request, urllib.parse, urllib.error
import ssl
import re

ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE
url = "http://py4e-data.dr-chuck.net/known_by_Aidian.html"

#to repeat 7 times#
for i in range(7):
    html = urllib.request.urlopen(url, context=ctx).read()
    soup = BeautifulSoup(html, 'html.parser')
    tags = soup('a')
    count = 0
    for tag in tags:
        count = count +1
   
        #make it stop at position 3#
        if count>18:
            break
        url = tag.get('href', None)

print(url)
```
# Assignment Wk 5 Extracting Data from XML



```
import urllib.request, urllib.parse, urllib.error
import xml.etree.ElementTree as ET

url = 'http://py4e-data.dr-chuck.net/comments_1240428.xml'
if len(url) < 1:
    url = "http://py4e-data.dr-chuck.net/comments_1240428.xml"
print ("Retrieving " + url)

xml = urllib.request.urlopen(url).read()
print ("Retrieved: " + str(len(xml)) + " characters")

tree = ET.fromstring(xml)

counts =  tree.findall('.//count')
print ("Count: " + str(len(counts)))

accumulator = 0

for count in counts:
    accumulator += int(count.text)

print ("Sum:" + str(accumulator))
```

# Assignment Week 6 Extracting Data from JSON

```
import urllib.request, urllib.parse, urllib.error
import json
count = 0

url = "http://py4e-data.dr-chuck.net/comments_1240429.json"
print ("retrieving URL. Stand by.")
uh = urllib.request.urlopen(url)
data= uh.read()

info = json.loads(data)
for item in info["comments"]:
	#print item["count"]
	number = int(item["count"])
	count = count + number
print (count)
```


# Assignment - Calling a JSON API

```
import urllib.request, urllib.parse, urllib.error
import json
import ssl

api_key = False
# If you have a Google Places API key, enter it here
# api_key = 'AIzaSy___IDByT70'
# https://developers.google.com/maps/documentation/geocoding/intro

if api_key is False:
    api_key = 42
    serviceurl = 'http://py4e-data.dr-chuck.net/json?'
else :
    serviceurl = 'https://maps.googleapis.com/maps/api/geocode/json?'

# Ignore SSL certificate errors
ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE

while True:
    address = "AGH University of Science and Technology"
    if len(address) < 1: break

    parms = dict()
    parms['address'] = address
    if api_key is not False: parms['key'] = api_key
    url = serviceurl + urllib.parse.urlencode(parms)

    print('Retrieving', url)
    uh = urllib.request.urlopen(url, context=ctx)
    data = uh.read().decode()
    print('Retrieved', len(data), 'characters')

    try:
        js = json.loads(data)
    except:
        js = None

    if not js or 'status' not in js or js['status'] != 'OK':
        print('==== Failure To Retrieve ====')
        print(data)
        continue

    print(json.dumps(js, indent=4))

    lat = js['results'][0]['geometry']['location']['lat']
    lng = js['results'][0]['geometry']['location']['lng']
    print('lat', lat, 'lng', lng)
    location = js['results'][0]['formatted_address']
    print(location)
```
