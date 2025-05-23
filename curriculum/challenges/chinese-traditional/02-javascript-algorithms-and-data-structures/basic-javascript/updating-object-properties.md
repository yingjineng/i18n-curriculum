---
id: 56bbb991ad1ed5201cd392d1
title: 更新對象屬性
challengeType: 1
forumTopicId: 18336
dashedName: updating-object-properties
---

# --description--

After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

舉個例子，讓我們看看 `ourDog`：

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```

既然他是一個特別愉快的狗，讓我們將他的名字更改爲字符串 `Happy Camper`。 這有兩種方式來更新對象的 name 屬性： `ourDog.name = "Happy Camper";` 或 `ourDog["name"] = "Happy Camper";`。更新後，`ourDog.name` 的值就不再是 `Camper`，而是 `Happy Camper`。

# --instructions--

更新 `myDog` 對象的 name 屬性。 讓它的名字從 `Coder` 變成 `Happy Coder`。 你可以使用點號表示法或方括號表示法來完成此挑戰。

# --hints--

更新 `myDog` 的 `name` 屬性，使其等於 `Happy Coder`。

```js
assert(/happy coder/gi.test(myDog.name));
```

不要修改 `myDog` 的定義。

```js
assert(/"name": "Coder"/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return z;})(myDog);
```

## --seed-contents--

```js
// Setup
const myDog = {
  "name": "Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};

// Only change code below this line

```

# --solutions--

```js
const myDog = {
  "name": "Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};
myDog.name = "Happy Coder";
```
