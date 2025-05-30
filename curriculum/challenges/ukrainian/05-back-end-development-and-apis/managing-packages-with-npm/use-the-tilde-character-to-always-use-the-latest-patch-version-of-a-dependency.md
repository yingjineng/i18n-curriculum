---
id: 587d7fb5367417b2b2512c02
title: Використайте тильду, щоб завжди використовувати останню патч версію залежності
challengeType: 2
forumTopicId: 301532
dashedName: use-the-tilde-character-to-always-use-the-latest-patch-version-of-a-dependency
---

# --description--

В останньому завданні ви сказали npm включати тільки конкретну версію пакету. Це корисний спосіб призупинити блокування своїх залежностей, якщо вам потрібно переконатися, що різні частини проєкту залишаються сумісними між собою. Але в більшості випадків не варто пропускати виправлення помилок, оскільки вони часто містять важливі патчі безпеки і (як можна сподіватися) нічого при цьому не порушують.

Щоб npm-залежність оновилася до останньої версії PATCH, можна встановити префікс версії залежностей символом тильди (`~`). Ось приклад того, як дозволити оновлення до будь-якої версії `1.3.x`.

```json
"package": "~1.3.8"
```

# --instructions--

У файлі package.json вашим поточним правилом для оновлення `@freecodecamp/example` є використання конкретної версії (`1.2.13`). Але тепер потрібна остання версія `1.2.x`.

Використайте символ тильда (`~`), щоб встановити префікс версії `@freecodecamp/example` у своїх залежностях і дозволити npm оновлення до будь-якої версії _патч_.

**Примітка:** номери версій не слід змінювати.

# --hints--

`"dependencies"` має містити `"@freecodecamp/example"`.

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.property(
        packJson.dependencies,
        '@freecodecamp/example',
        '"dependencies" does not include "@freecodecamp/example"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Версія `"@freecodecamp/example"` має відповідати `"~1.2.13"`.

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.match(
        packJson.dependencies["@freecodecamp/example"],
        /^\~1\.2\.13/,
        'Wrong version of "@freecodecamp/example". It should be ~1.2.13'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

