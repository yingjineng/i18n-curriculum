---
id: 5e9a093a74c4063ca6f7c154
title: Arreglos de NumPy
challengeType: 11
videoId: VDYVFHBL1AM
bilibiliIds:
  aid: 890607366
  bvid: BV1zP4y1h7FR
  cid: 409011400
dashedName: numpy-arrays
---

# --description--

*En lugar de usar notebooks.ai como se muestra en el vídeo, puede utilizar Google Colab en su lugar.*

Más recursos:

-  <a href="https://github.com/ine-rmotr-curriculum/freecodecamp-intro-to-numpy" target="_blank" rel="noopener noreferrer nofollow">Notebooks en GitHub</a>
-  <a href="https://colab.research.google.com/github/googlecolab/colabtools/blob/master/notebooks/colab-github-demo.ipynb" target="_blank" rel="noopener noreferrer nofollow">Cómo abrir Notebooks desde GitHub usando Google Colab.</a>

# --questions--

## --text--

¿Qué imprimirá el siguiente código?

```py
A = np.array([
    ['a', 'b', 'c'],
    ['d', 'e', 'f'],
    ['g', 'h', 'i']
])

print(A[:, :2])
```

## --answers--

```py
[['a' 'b']]
```

---

```py
[['b' 'c']
['e' 'f']
['h' 'i']]
```

---

```py
[['a' 'b']
['d' 'e']
['g' 'h']]
```

## --video-solution--

3

