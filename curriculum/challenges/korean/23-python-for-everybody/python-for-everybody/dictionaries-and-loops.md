---
id: 5e7b9f0a0b6c005b0e76f069
title: 사전 및 루프
challengeType: 11
videoId: EEmekKiKG70
bilibiliIds:
  aid: 589401038
  bvid: BV1eq4y1X7xU
  cid: 376387132
dashedName: dictionaries-and-loops
---

# --description--

More resources:

\- <a href="https://www.youtube.com/watch?v=PrhZ9qwBDD8" target="_blank" rel="noopener noreferrer nofollow">Exercise</a>

# --questions--

## --text--

다음 코드는 무엇을 출력하나요?:

```python
counts = { 'chuck' : 1 , 'annie' : 42, 'jan': 100}
for key in counts:
    if counts[key] > 10:
        print(key, counts[key])
```

## --answers--

<pre>annie 42
jan 100</pre>

---

<pre>chuck 1
annie 42
jan 100</pre>

---

<pre>chuck 1</pre>

---

<pre>[Error]</pre>

## --video-solution--

1
