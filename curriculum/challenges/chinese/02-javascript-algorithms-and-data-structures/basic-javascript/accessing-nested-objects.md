---
id: 56533eb9ac21ba0edf2244cc
title: 访问嵌套对象
challengeType: 1
forumTopicId: 16161
dashedName: accessing-nested-objects
---

# --description--

The sub-properties of objects can be accessed by chaining together the dot or bracket notation.

这是一个嵌套对象：

```js
const ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};

ourStorage.cabinet["top drawer"].folder2;
ourStorage.desk.drawer;
```

`ourStorage.cabinet["top drawer"].folder2` 将会是字符串 `secrets`，并且 `ourStorage.desk.drawer` 将会是字符串 `stapler`。

# --instructions--

访问 `myStorage` 对象并将 `glove box` 属性的内容赋值给 `gloveBoxContents` 变量。 在可能的情况下，对所有的属性使用点号，否则使用方括号。

# --hints--

`gloveBoxContents` 应该等于字符串 `maps`。

```js
assert(gloveBoxContents === 'maps');
```

你的代码应该尽可能使用点号来访问 `myStorage`。

```js
assert.match(code, /myStorage\.car\.inside/);
```

应该用 `const` 声明 `gloveBoxContents`。

```js
assert.match(code, /const\s+gloveBoxContents\s*=/);
```

你不应该更改 `myStorage` 对象。

```js
const expectedMyStorage = {
  "car":{
    "inside":{
      "glove box":"maps",
      "passenger seat":"crumbs"
    },
    "outside":{
      "trunk":"jack"
    }
  }
};
assert.deepStrictEqual(myStorage, expectedMyStorage);
```

# --seed--

## --after-user-code--

```js
(function(x) { 
  if(typeof x != 'undefined') { 
    return "gloveBoxContents = " + x;
  }
  return "gloveBoxContents is undefined";
})(gloveBoxContents);
```

## --seed-contents--

```js
const myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

const gloveBoxContents = undefined;
```

# --solutions--

```js
const myStorage = {
  "car":{
    "inside":{
      "glove box":"maps",
      "passenger seat":"crumbs"
    },
    "outside":{
      "trunk":"jack"
    }
  }
};
const gloveBoxContents = myStorage.car.inside["glove box"];
```
