# python-challenge-solution

Play the site [pythonchallenge](http://www.pythonchallenge.com/)

# Level
## Level 0
```python
print pow(2,38)
# Get url http://www.pythonchallenge.com/pc/def/274877906944.html
```

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
# Translate string to get another hint
# We have tranlate current url to encoding form. 
# Get the new url is http://www.pythonchallenge.com/pc/def/ocr.html
```
