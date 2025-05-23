---
id: 56bbb991ad1ed5201cd392d1
title: 更新对象属性
challengeType: 1
forumTopicId: 18336
dashedName: updating-object-properties
---

# --description--

After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

举个例子，让我们看看 `ourDog`：

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```

既然他是一个特别愉快的狗，让我们将他的名字更改为字符串 `Happy Camper`。 这有两种方式来更新对象的 name 属性： `ourDog.name = "Happy Camper";` 或 `ourDog["name"] = "Happy Camper";`。更新后，`ourDog.name` 的值就不再是 `Camper`，而是 `Happy Camper`。

# --instructions--

更新 `myDog` 对象的 name 属性。 让它的名字从 `Coder` 变成 `Happy Coder`。 你可以使用点号表示法或方括号表示法来完成此挑战。

# --hints--

更新 `myDog` 的 `name` 属性，使其等于 `Happy Coder`。

```js
assert(/happy coder/gi.test(myDog.name));
```

不要修改 `myDog` 的定义。

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
