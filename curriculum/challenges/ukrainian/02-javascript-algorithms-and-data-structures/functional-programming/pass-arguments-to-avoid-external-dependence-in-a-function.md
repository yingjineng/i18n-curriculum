---
id: 587d7b8e367417b2b2512b5f
title: Передача аргументів для уникнення зовнішньої залежності у функції
challengeType: 1
forumTopicId: 301234
dashedName: pass-arguments-to-avoid-external-dependence-in-a-function
---

# --description--

The last challenge was a step closer to functional programming principles, but there is still something missing.

Ми не змінили значення глобальної змінної, але функція `incrementer` не буде працювати без глобальної змінної `fixedValue`.

Інший принцип функційного програмування — завжди оголошувати свої залежності відкрито. Це означає, що якщо функція залежить від змінної чи об’єкта, тоді ця змінна чи об’єкт передаються прямо до функції як аргумент.

З цього принципу випливає декілька хороших наслідків. Цю функцію легше протестувати, ви знаєте її вхідні дані і вона ні від чого не залежить у вашій програмі.

Таким чином ви будете впевненішими при зміні, видаленні чи додаванні нового коду. Ви знатимете, що можна змінити і бачитимете, де розміщені потенційні пастки.

Зрештою, функція завжди виробляє однакові вихідні дані для однакових вхідних даних, незалежно від того, яка частина коду виконує їх.

# --instructions--

Оновимо функцію `incrementer` так, щоб вона чітко оголошувала свої залежності.

Напишіть функцію `incrementer` так, щоб вона приймала аргумент, а потім повертала значення, збільшене на один.

# --hints--

Ваша функція `incrementer` не повинна змінювати значення `fixedValue` (дорівнює `4`).

```js
assert(fixedValue === 4);
```

Ваша функція `incrementer` повинна приймати аргумент.

```js
assert(incrementer.length === 1);
```

Ваша функція `incrementer` повинна повертати значення, яке більше на одиницю за `fixedValue`.

```js
const __newValue = incrementer(fixedValue);
assert(__newValue === 5);
```

# --seed--

## --seed-contents--

```js
// The global variable
let fixedValue = 4;

// Only change code below this line
function incrementer() {


  // Only change code above this line
}
```

# --solutions--

```js
let fixedValue = 4;

function incrementer(fixedValue) {
  return fixedValue + 1;
}
```
