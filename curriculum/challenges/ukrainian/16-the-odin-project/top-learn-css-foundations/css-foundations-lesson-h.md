---
id: 63ee354c0d8d4841c3a70921
title: Основи CSS. Урок №8
challengeType: 19
dashedName: css-foundations-lesson-h
---

# --description--

Вбудований `CSS` дозволяє додавати стилі одразу до елементів `HTML`, хоча цей метод нерекомендований:

```html
<body>
  <div style="color: white; background-color: black;">...</div>
</body>
```

Потрібно зазначити, що тут немає селекторів, оскільки стилі додаються одразу до початкового тегу `<div>`. Ви маєте атрибут `style`, значення якого всередині пари лапок є оголошеннями.

Якщо вам потрібно додати унікальний стиль для одного елементу, цей метод підходить. Однак це нерекомендований спосіб додавання CSS до HTML через декілька причин:

Все може швидко стати досить заплутаним, як тільки ви почнете додавати багато оголошень до одного елемента, забруднюючи свій файл HTML. Якщо ви хочете надати багатьом елементам одного стилю, ви копіюватимете та вставлятимете їх по декілька разів, що призведе до непотрібного повторення. Будь-який вбудований CSS перекриватиме інші два методи, що може призвести до несподіваних результатів. (Ми не будемо вдаватися в деталі, але насправді це можна використати на користь).

# --questions--

## --text--

Що з переліченого є головним недоліком вбудованого CSS?

## --answers--

Все може швидко стати досить заплутаним, як тільки ви почнете додавати багато оголошень до одного елемента, забруднюючи свій файл HTML.

---

Вбудований CSS вимагає використання селекторів, що може бути складним для початківців.

---

Будь-який вбудований CSS перекриватиме інші два методи (внутрішній та зовнішній), що може призвести до несподіваних результатів.


## --video-solution--

3
