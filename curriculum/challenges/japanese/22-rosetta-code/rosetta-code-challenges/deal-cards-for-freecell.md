---
id: 59694356a6e7011f7f1c5f4e
title: フリーセルのカードを配る
challengeType: 1
forumTopicId: 302246
dashedName: deal-cards-for-freecell
---

# --description--

*フリーセル*は、ポール・アルフィレ (Paul Alfille) が 1978 年に PLATO システムに導入したソリティアというカードゲームです。 Microsoft のジム・ホーンは、ゲームの名称を「フリーセル」に改め、DOS、続いて Windows 向けにゲームを再実装しました。 このバージョンでは、32000 のゲーム番号が導入されました。

ゲームが普及し、ジム・ホーンがアルゴリズムを開示したため、他のフリーセル実装でも Microsoft と同様のアルゴリズムでカードが配られるようになりました。 カードの配り方には 1 から 32000 まで番号が付けられています。 Microsoft の新しいバージョンでは、1 から 1000000 までの番号が付けられた 100 万のゲーム番号があります。一部の実装では、この範囲外の番号も使用されています。

このアルゴリズムでは Microsoft C の線形合同法が使用されています。

<ul>
  <li>$state_{n + 1} \equiv 214013 \times state_n + 2531011 \pmod{2^{31}}$</li>
  <li>$rand_n = state_n \div 2^{16}$</li>
  <li>$rand_n$ は 0 から 32767 の範囲です。</li>
</ul>

アルゴリズムは以下のとおりです。

<ol>
  <li>RNG にゲーム番号を与えます。
  </li><li>52 枚のカードの配列を作成します。クラブのエース、ダイヤモンドのエース、ハートのエース、スペードのエース、クラブの 2、ダイヤモンドの 2、…と続き、エース、2、3、4、5、6、7、8、9、10、ジャック、クイーン、キングまで続きます。 配列インデックスは 0 から 51 で、クラブのエースは 0、スペードのキングは 51 です。</li>
  <li>配列が空になるまで、以下の手順を実行します。</li>
    <ul>
      <li><i>インデックス</i>≡<i>次の乱数</i> (を<i>配列の長さ</i>で割った余り) の場所にあるカードを選択します。</li>
      <li>このランダムなカードを配列の最後のカードと交換します。</li>
      <li>このランダムなカードを配列から削除します (配列の長さが 1 減る)。</li>
      <li>このランダムなカードを配ります。</li>
    </ul>
  <li>52 枚すべてのカードを、表を上にして 8 列に配ります。 最初の 8 枚のカードが 8 列に配られ、その上に次の 8 枚のカードが配られ、と続いていきます。</li>
</ol>

**例:**

**カードを配る順番**

<pre> 1  2  3  4  5  6  7  8
 9 10 11 12 13 14 15 16
17 18 19 20 21 22 23 24
25 26 27 28 29 30 31 32
33 34 35 36 37 38 39 40
41 42 43 44 45 46 47 48
49 50 51 52</pre>

**ゲーム #1**

```js
[
  ['JD', '2D', '9H', 'JC', '5D', '7H', '7C', '5H'],
  ['KD', 'KC', '9S', '5S', 'AD', 'QC', 'KH', '3H'],
  ['2S', 'KS', '9D', 'QD', 'JS', 'AS', 'AH', '3C'],
  ['4C', '5C', 'TS', 'QH', '4H', 'AC', '4D', '7S'],
  ['3S', 'TD', '4S', 'TH', '8H', '2C', 'JH', '7D'],
  ['6D', '8S', '8D', 'QS', '6C', '3D', '8C', 'TC'],
  ['6S', '9C', '2H', '6H']
]
```

**ゲーム #617**

```js
[
  ['7D', 'AD', '5C', '3S', '5S', '8C', '2D', 'AH'],
  ['TD', '7S', 'QD', 'AC', '6D', '8H', 'AS', 'KH'],
  ['TH', 'QC', '3H', '9D', '6S', '8D', '3D', 'TC'],
  ['KD', '5H', '9S', '3C', '8S', '7H', '4D', 'JS'],
  ['4C', 'QS', '9C', '9H', '7C', '6H', '2C', '2S'],
  ['4S', 'TS', '2H', '5D', 'JC', '6C', 'JH', 'QH'],
  ['JD', 'KS', 'KC', '4H']
]
```

# --instructions--

ゲーム番号を受け取り、このアルゴリズムと同じ順序でカードを配る関数を作成します。 この関数はフリーセルボードを表す 2 次元配列を返します。

# --hints--

`dealFreeCell` という関数です。

```js
assert(typeof dealFreeCell === 'function');
```

`dealFreeCell(seed)` はオブジェクトを返します。

```js
assert(typeof dealFreeCell(1) === 'object');
```

`dealFreeCell(seed)` は長さ 7 の配列を返します。

```js
assert(dealFreeCell(1).length === 7);
```

`dealFreeCell(1)` は例「Game #1」と同一の配列を返します。

```js
assert.deepEqual(dealFreeCell(1), game1);
```

`dealFreeCell(617)` は「Game #617」と同一の配列を返します。

```js
assert.deepEqual(dealFreeCell(617), game617);
```

# --seed--

## --after-user-code--

```js
const replaceThis = 3;
const game1 = [
  ['JD', '2D', '9H', 'JC', '5D', '7H', '7C', '5H'],
  ['KD', 'KC', '9S', '5S', 'AD', 'QC', 'KH', '3H'],
  ['2S', 'KS', '9D', 'QD', 'JS', 'AS', 'AH', '3C'],
  ['4C', '5C', 'TS', 'QH', '4H', 'AC', '4D', '7S'],
  ['3S', 'TD', '4S', 'TH', '8H', '2C', 'JH', '7D'],
  ['6D', '8S', '8D', 'QS', '6C', '3D', '8C', 'TC'],
  ['6S', '9C', '2H', '6H']
];
const game617 = [
  ['7D', 'AD', '5C', '3S', '5S', '8C', '2D', 'AH'],
  ['TD', '7S', 'QD', 'AC', '6D', '8H', 'AS', 'KH'],
  ['TH', 'QC', '3H', '9D', '6S', '8D', '3D', 'TC'],
  ['KD', '5H', '9S', '3C', '8S', '7H', '4D', 'JS'],
  ['4C', 'QS', '9C', '9H', '7C', '6H', '2C', '2S'],
  ['4S', 'TS', '2H', '5D', 'JC', '6C', 'JH', 'QH'],
  ['JD', 'KS', 'KC', '4H']
];
```

## --seed-contents--

```js
function dealFreeCell(seed) {

  return true;
}
```

# --solutions--

```js
// RNG
function FreeCellRNG(seed) {
  return {
    lastNum: seed,
    next() {
      this.lastNum = ((214013 * this.lastNum) + 2531011) % (Math.pow(2, 31));
      return this.lastNum >> 16;
    }
  };
}
// Get cards
function getDeck() {
  const ranks = ['A', '2', '3', '4', '5', '6', '7', '8', '9', 'T', 'J', 'Q', 'K'];
  const suits = ['C', 'D', 'H', 'S'];
  const cards = [];
  for (let i = 0; i < ranks.length; i += 1) {
    for (let j = 0; j < suits.length; j += 1) {
      cards.push(`${ranks[i]}${suits[j]}`);
    }
  }
  return cards;
}
function dealFreeCell(seed) {
  const rng = FreeCellRNG(seed);
  const deck = getDeck();

  const dealtCards = [[], [], [], [], [], [], []];
  let currentColumn = 0;
  let currentRow = 0;

  let rand;
  let temp;
  let card;
  while (deck.length > 0) {
    // Choose a random card
    rand = rng.next() % deck.length;

    // Swap this random card with the last card in the array
    temp = deck[deck.length - 1];
    deck[deck.length - 1] = deck[rand];
    deck[rand] = temp;

    // Remove this card from the array
    card = deck.pop();

    // Deal this card
    dealtCards[currentRow].push(card);
    currentColumn += 1;
    if (currentColumn === 8) {
      currentColumn = 0;
      currentRow += 1;
    }
  }

  return dealtCards;
}
```
