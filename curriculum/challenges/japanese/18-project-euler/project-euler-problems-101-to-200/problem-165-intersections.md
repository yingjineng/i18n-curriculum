---
id: 5900f4111000cf542c50ff24
title: '問題 165: 交点'
challengeType: 1
forumTopicId: 301799
dashedName: problem-165-intersections
---

# --description--

線分は 2 つの端点によって一意に定義されます。 平面上にある 2 本の線分について考えると、共有点がない、共有点が 1 つある、共有点が無数にある、という 3 つの可能性があります。

Moreover when two segments have exactly one point in common it might be the case that common point is an endpoint of either one of the segments or of both. 2 本の線分の共有点がいずれの線分の端点でもない場合、それは両方の線分の内点です。

点 $T$ が 2 本の線分 $L_1$ と $L_2$ の唯一の共有点であり、かつ、$T$ が両方の線分の内点である場合、$L_1$ と $L_2$ の共有点 $T$ を $L_1$ と $L_2$ の「真の交点」と呼ぶことにします。

3 本の線分 $L_1$, $L_2$, $L_3$ について考えます。

$$\begin{align}   & L_1: (27, 44) \\;\text{から}\\; (12, 32) \\\\
  & L_2: (46, 53) \\;\text{から}\\; (17, 62) \\\\   & L_3: (46, 70) \\;\text{から}\\; (22, 40) \\\\
\end{align}$$

線分 $L_2$ と $L_3$ が真の交点を持つことを確認できます。 なお、$L_3$ の一方の端点 (22, 40) は $L_1$ 上にありますが、これを真の交点とはみなしません。 $L_1$ と $L_2$ に共有点はありません。 したがって、この 3 本の線分には真の交差点が 1 つあります。

次に、5000 本の線分について同じことをします。 このために、"Blum Blum Shub" と呼ばれる擬似乱数法を使用して 20000 個の数を生成します。

$$\begin{align}   & s_0 = 290797 \\\\
  & s_{n + 1} = s_n × s_n (\text{mod}\\; 50515093) \\\\   & t_n = s_n (\text{mod}\\; 500) \\\\
\end{align}$$

それぞれの線分を作成するには、4 つの連続数字 $t_n$ を使用します。 つまり、最初の線分は次によって与えられます。

($_t$1, $t_2$) から ($t_3$, $t_4$)

上の生成法によって計算される最初の 4 つの数は 27, 144, 12, 232 です。 したがって、最初の線分は (27, 144) から (12, 232) となります。

これらの 5000 本の線分には、相異なる真の交点がいくつありますか。

# --hints--

`distinctIntersections()` は `2868868` を返す必要があります 。

```js
assert.strictEqual(distinctIntersections(), 2868868);
```

# --seed--

## --seed-contents--

```js
function distinctIntersections() {

  return true;
}

distinctIntersections();
```

# --solutions--

```js
// solution required
```
