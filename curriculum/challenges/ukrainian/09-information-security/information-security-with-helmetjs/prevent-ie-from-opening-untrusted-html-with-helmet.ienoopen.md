---
id: 587d8248367417b2b2512c3b
title: Перешкоджайте IE від відкриття ненадійного HTML за допомогою helmet.ieNoOpen()
challengeType: 2
forumTopicId: 301584
dashedName: prevent-ie-from-opening-untrusted-html-with-helmet-ienoopen
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Деякі вебзастосунки обслуговуватимуть ненадійний HTML для завантаження. Деякі версії Internet Explorer відкривають ці HTML-файли в контексті вашого сайту за замовчуванням. Через це ненадійна сторінка HTML може почати робити погані речі вашим сторінкам. Це проміжне програмне забезпечення встановлює заголовок X-Frame-Options на noopen (не відкривати). Це дозволить користувачам Internet Explorer виконувати завантаження на надійних сайтах.

# --instructions--

Використайте метод `helmet.ieNoOpen()` на своєму сервері.

# --hints--

Проміжне ПЗ helmet.ieNoOpen() повинне бути встановлене правильно

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'ienoopen');
      assert.equal(data.headers['x-download-options'], 'noopen');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

