---
id: 5e7b9f0d0b6c005b0e76f075
title: 'Redes: Usando urllib en Python'
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

¿Cuál seriá la salida del siguiente código?:

```python
import urllib.request
fhand = urllib.request.urlopen('http://data.pr4e.org/romeo.txt')
for line in fhand:
    print(line.decode().strip())
```

## --answers--

Sólo el contenido de "romeo.txt".

---

Un encabezado y el contenido de "romeo.txt".

---

Un encabezado, un pie de página y el contenido de "romeo.txt".

## --video-solution--

1

