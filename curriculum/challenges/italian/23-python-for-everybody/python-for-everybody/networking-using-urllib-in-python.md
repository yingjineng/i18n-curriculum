---
id: 5e7b9f0d0b6c005b0e76f075
title: 'Networking: usare urllib in Python'
challengeType: 11
videoId: 7lFM1T_CxBs
bilibiliIds:
  aid: 546908270
  bvid: BV1Xq4y1H7e6
  cid: 377331524
dashedName: networking-using-urllib-in-python
---

# --questions--

## --text--

What will the output of the following code be like?:

```python
import urllib.request
fhand = urllib.request.urlopen('http://data.pr4e.org/romeo.txt')
for line in fhand:
    print(line.decode().strip())
```

## --answers--

Solo i contenuti di "romeo.txt".

---

Un'intestazione e il contenuto di "romeo.txt".

---

Un'intestazione, un piè di pagina e il contenuto di "romeo.txt".

## --video-solution--

1

