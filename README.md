# python-challenge-solution

Play the site [pythonchallenge](http://www.pythonchallenge.com/)

# Level
## Level 0
```python
print pow(2,38)
```
Get url http://www.pythonchallenge.com/pc/def/274877906944.html

## Level 1
```python
s="g fmnc wms bgblr rpylqjyrc gr zw fylb. rfyrq ufyr amknsrcpq ypc dmp. bmgle gr gl zw fylb gq glcddgagclr ylb rfyr'q ufw rfgq rcvr gq qm jmle. sqgle qrpgle.kyicrpylq() gq pcamkkclbcb. lmu ynnjw ml rfc spj."
o=""
t=""
for i in s:
	t=chr(ord(i)+2)
	if i==' ' or i=='.' or i=='\'':
		t=i
	elif ord(i)+2>122:
		t=chr((ord(i)+2)%122+96)
	o+=t
print o
# Translate string to get another hint.
# We have tranlate current url to encoding form. 
```
Get the new url is http://www.pythonchallenge.com/pc/def/ocr.html.

## Level 2
```python
f=open('test.txt', 'r')
d={}
for line in f:
	for c in line:
		if c in d:
			d[c]=d[c]+1
		else:
			d[c]=1
for k, v in d.iteritems():
	print k, v
# View the page source then save the mess code into the test.txt file.
# Get the rare characters are "aeilquty" then reorder it to a word "equality".
```
The new url is http://www.pythonchallenge.com/pc/def/equality.html.

## Level 3
```python
import re
f=open('test.txt', 'r')
s=""
for line in f:
	s+=line
m = re.findall('[a-z]{1}[A-Z]{3}([a-z])[A-Z]{3}[a-z]{1}', s)
print ''.join(m)
# View the page source then save the mess code into the test.txt file.
# Run the snippet to get a string "linkedlist".
```
The new url is http://www.pythonchallenge.com/pc/def/linkedlist.html

## Level 4
```python
import urllib2
import sys

no="12345"
for i in range(500):
	sUrl="http://www.pythonchallenge.com/pc/def/linkedlist.php?nothing="+no
	print str(i)+". "+sUrl
	userAgent='Mozilla/4.0 (compatible; MSIE 5.5; Windows NT)'
	headers = { 'User-Agent': userAgent}
	request = urllib2.Request(sUrl, headers=headers)
	response = urllib2.urlopen(request)
	sPage = response.read()
	unicodePage = sPage.decode("utf-8")
	no=sPage.split(' ')[-1]
# Run this snippet will get a page "peak.html"
```
The new url is http://www.pythonchallenge.com/pc/def/peak.html

## Level 5
```python
import pickle 
favorite_color = pickle.load( open( "test.txt", "r" ) )
print '\n'.join([''.join([p[0]*p[1] for p in data]) for data in favorite_color])
# The pickle load list likes a run-length list.
# We get a big ASCII word "channel".
```
The new url is http://www.pythonchallenge.com/pc/def/channel.html

## Level 6
```python
import zipfile
import StringIO
import urllib
z = zipfile.ZipFile(StringIO.StringIO(urllib.urlopen('http://www.pythonchallenge.com/pc/def/channel.zip').read()))
zpp = []
f='90052.txt'
for i in range(len(z.namelist())):
    zpp.append(f)
    print ''.join([z.getinfo('%s'%p).comment for p in zpp])
    n=z.read(f).split(' ')[-1]
    f=n+'.txt'
```
The new url is http://www.pythonchallenge.com/pc/def/hockey.html
