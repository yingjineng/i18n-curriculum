---
id: 65e1a2ea500d930ce8ed90a9
title: Вивчіть змінні та оператори. Урок №6
challengeType: 15
dashedName: learn-variables-and-operators-lesson-f
---

# --description--

Ознайомимось з особливостями операторів JavaScript, які виходять за межі шкільної математики.

Зазвичай оператор `+` додає числа.

А ось якщо бінарний `+` застосувати до рядків, він об’єднає їх:

```js
let s = "my" + "string";
console.log(s); // mystring
```

Зверніть увагу, що якщо будь-який з операндів є рядком, то інший теж перетворюється на рядок.

Наприклад:

```js
console.log(1 + '2'); // '12'
console.log('1' + 2); // '12'
```

Неважливо, який операнд є рядком: перший чи другий.

Ось складніший приклад:

```js
console.log(2 + 2 + '1') // "41" and not "221"
```

Тут оператори працюють по черзі. Перший `+` додає два числа, тому повертає `4`, а наступний `+` додає рядок `1`, отже `4 + '1' = '41'`.

```js
console.log('1' + 2 + 2) // "122" and not "14"
```

Перший `+` об’єднує рядок та число, тому повертає `'12'`, а наступний `+` додає `2`, отже `'12' + 2 = '122'`.

Бінарний `+` — це єдиний оператор, який підтримує рядки таким чином. Інші математичні оператори працюють лише з числами та завжди перетворюють операнди на числа.

Ось віднімання та ділення:

```js
console.log( 6 - '2' ); // 4, converts '2' to a number
console.log( '6' / '2' ); // 3, converts both operands to numbers
```

# --questions--

## --text--
Дано наступний фрагмент коду. Яким буде результат, якщо враховувати поведінку оператора `+` зі змішаними типами даних в JavaScript?

```js
console.log('3' + 2 - 1);
```

## --answers--

`31`, оскільки оператор `+` об’єднує рядок та число перед відніманням.

---

`32`, оскільки `+` об’єднує рядок та число перед відніманням.

---

`4`, оскільки спочатку всі операнди перетворюються на числа.

---

`321`, оскільки оператор `-` не підтримує рядки.

## --video-solution--

1
