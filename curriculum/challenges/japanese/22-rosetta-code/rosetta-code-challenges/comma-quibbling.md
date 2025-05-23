---
id: 596e414344c3b2872167f0fe
title: コンマの追加
challengeType: 1
forumTopicId: 302234
dashedName: comma-quibbling
---

# --description--

<a href="https://rosettacode.org/wiki/Comma_quibbling" target="_blank" rel="noopener noreferrer nofollow">カンマキブリング</a>はもともとエリック・リッパートが彼のブログで提示したタスクです。

# --instructions--

リスト / シーケンスからの入力単語の連結である文字列を出力する関数を作成します。

<ol>
  <li>単語を入力しなかった場合、2 つの中括弧文字 (<code>"{}"</code>) だけの出力文字列が生成されます。</li>
  <li>1 単語、例えば <code>["ABC"]</code>、だけを入力した場合、<code>"{ABC}"</code> のように、2 つの中括弧の中にその単語が出力文字列として生成されます。</li>
  <li>2 つの単語、例えば <code>["ABC", "DEF"]</code>、を入力した場合、<code>"{ABC and DEF}"</code> のように、文字列 <code>" and "</code> に区切られた 2 つの単語が、2 つの中括弧の中に出力文字列として生成されます。</li>
  <li>3 つ以上の単語、 例えば <code>["ABC", "DEF", "G", "H"]</code> を入力した場合、<code>"{ABC, DEF, G and H}"</code> のように、最後の単語以外のすべての単語は、<code>", "</code> で区切られ、最後の単語は <code>" and "</code> で区切られ、すべての単語が中括弧の中に出力文字列として生成されます。</li>
</ol>

次の一連の入力によりこのページに出力表示して、関数をテストします。

<ul>
  <li>[] # (入力単語なし)</li>
  <li>["ABC"]</li>
  <li>["ABC", "DEF"]</li>
  <li>["ABC", "DEF", "G", "H"]</li>
</ul>

**注記:** このタスクで、単語は大文字の空でない文字列です。

# --hints--

`quibble` という関数があります。

```js
assert(typeof quibble === 'function');
```

`quibble(["ABC"])` は文字列を返します。

```js
assert(typeof quibble(['ABC']) === 'string');
```

`quibble([])` は "{}" を返します。

```js
assert.equal(quibble(testCases[0]), results[0]);
```

`quibble(["ABC"])` は `"{ABC}"` を返します。

```js
assert.equal(quibble(testCases[1]), results[1]);
```

`quibble(["ABC", "DEF"])` は `"{ABC and DEF}"` を返します。

```js
assert.equal(quibble(testCases[2]), results[2]);
```

`quibble(["ABC", "DEF", "G", "H"])` は `"{ABC, DEF, G and H}"` を返します。

```js
assert.equal(quibble(testCases[3]), results[3]);
```

# --seed--

## --after-user-code--

```js
const testCases = [[], ["ABC"], ["ABC", "DEF"], ["ABC", "DEF", "G", "H"]];
const results = ["{}", "{ABC}", "{ABC and DEF}", "{ABC, DEF, G and H}"];
```

## --seed-contents--

```js
function quibble(words) {

  return true;
}
```

# --solutions--

```js
function quibble(words) {
  return "{" +
    words.slice(0, words.length - 1).join(", ") +
   (words.length > 1 ? " and " : "") +
   (words[words.length - 1] || '') +
  "}";
}
```
