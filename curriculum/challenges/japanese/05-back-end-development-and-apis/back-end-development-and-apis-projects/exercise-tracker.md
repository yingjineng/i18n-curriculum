---
id: 5a8b073d06fa14fcfde687aa
title: エクササイズ記録アプリ
challengeType: 4
forumTopicId: 301505
dashedName: exercise-tracker
---

# --description--

<a href="https://exercise-tracker.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://exercise-tracker.freecodecamp.rocks</a> と同じような機能を持つ、フルスタック JavaScript アプリを構築してください。 プロジェクトに取り組むにあたり、以下の方法のうち 1 つを用いてコードを記述します。

-   <a href="https://github.com/freeCodeCamp/boilerplate-project-exercisetracker/" target="_blank" rel="noopener noreferrer nofollow">GitHub リポジトリ</a>をクローンし、ローカル環境でチャレンジを完了させる。
-   使い慣れたサイトビルダーを使用してプロジェクトを完了させる。 必ず GitHub リポジトリのすべてのファイルを取り込む。

# --instructions--

レスポンスは、以下の構造にしてください。

エクササイズ:

```js
{
  username: "fcc_test",
  description: "test",
  duration: 60,
  date: "Mon Jan 01 1990",
  _id: "5fb5853f734231456ccb3b05"
}
```

ユーザー:

```js
{
  username: "fcc_test",
  _id: "5fb5853f734231456ccb3b05"
}
```

ログ:

```js
{
  username: "fcc_test",
  count: 1,
  _id: "5fb5853f734231456ccb3b05",
  log: [{
    description: "test",
    duration: 60,
    date: "Mon Jan 01 1990",
  }]
}
```

** ヒント: ** `date` プロパティについては、`Date` API の `toDateString` メソッド を使用すると期待した出力が得られます。

# --hints--

サンプルの URL ではなく、自分で作成したプロジェクトを提出する必要があります。

```js
  assert(
    !/.*\/exercise-tracker\.freecodecamp\.rocks/.test(code)
  );
```

フォームデータ `username` を使用して `/api/users` への `POST` リクエストを実行することで、新しいユーザーを作成することができます。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  assert.isTrue(res.ok);
  if(!res.ok) {
    throw new Error(`${res.status} ${res.statusText}`)
  };
};
```

フォームデータ `username` を使用して `POST /api/users` を実行した際のレスポンスは、`username` プロパティおよび `_id` プロパティを持つオブジェクトです。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if (res.ok) {
    const { _id, username } = await res.json();
    assert.exists(_id);
    assert.exists(username);
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  }
};
```

`/api/users` への `GET` リクエストを実行することにより、すべてのユーザーのリストを取得できます。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users');
  assert.isTrue(res.ok);
  if(!res.ok) {
    throw new Error(`${res.status} ${res.statusText}`)
  };
};
```

`/api/users` への `GET` リクエストを実行すると、配列が返されます。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users');
  if(res.ok){
    const users = await res.json();
    assert.isArray(users);
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  };
};
```

`GET /api/users` から返される配列の各要素は、ユーザーの `username` および `_id` を含むオブジェクトリテラルです。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users');
  if(res.ok){
    const users = await res.json();
    const user = users[0];
    assert.exists(user);
    assert.exists(user.username);
    assert.exists(user._id);
    assert.isString(user.username);
    assert.isString(user._id);
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  };
};
```

`/api/users/:_id/exercises` への `POST` では、フォームデータ `description`、`duration`、および `date` (省略可) を指定できます。 日付を指定しない場合は、現在の日付が使用されます。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if (res.ok) {
    const { _id, username } = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: 'Mon Jan 01 1990'
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}&date=1990-01-01`
    });
  assert.isTrue(addRes.ok);
  if(!addRes.ok) {
    throw new Error(`${addRes.status} ${addRes.statusText}`)
  };
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  }
};
```

`POST /api/users/:_id/exercises` から返されるレスポンスは、エクササイズの各フィールドが追加されたユーザーオブジェクトです。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if (res.ok) {
    const { _id, username } = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: 'Mon Jan 01 1990'
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}&date=1990-01-01`
    });
    assert.isTrue(addRes.ok);
    if (!addRes.ok) {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    }
    const responseBody = await addRes.json();
    assert.isString(responseBody.description);
    assert.isNumber(responseBody.duration);
    assert.isString(responseBody.date);
    assert.equal(responseBody._id, expected._id);
    assert.equal(responseBody.username, expected.username);
    assert.equal(responseBody.description, expected.description);
    assert.equal(responseBody.duration, expected.duration);
    const receivedDate = new Date(responseBody.date);
    const expectedDate = new Date(expected.date); // Jan 1, 1990
    const allowedPreviousDate = new Date(expectedDate);
    allowedPreviousDate.setDate(expectedDate.getDate() - 1); // Dec 31, 1989
    const isValidDate =
      receivedDate.toDateString() === expectedDate.toDateString() ||
      receivedDate.toDateString() === allowedPreviousDate.toDateString();
    assert.isTrue(
      isValidDate,
      `Expected date to be ${expectedDate.toDateString()} or ${allowedPreviousDate.toDateString()}, but got ${receivedDate.toDateString()}`
    );
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  }
};
```

`/api/users/:_id/logs` への `GET` リクエストを実行すると、任意のユーザーのすべてのエクササイズログを取得できます。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if (res.ok) {
    const { _id, username } = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if (addRes.ok) {
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
    assert.isTrue(logRes.ok);
    if(!logRes.ok) {
      throw new Error(`${logRes.status} ${logRes.statusText}`)
    };
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    }
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  }
};
```

ユーザーログのリクエスト `GET /api/users/:_id/logs` は、そのユーザーに属するエクササイズの数を表す `count` プロパティを持つユーザーオブジェクトを返します。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if (res.ok) {
    const { _id, username } = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if (addRes.ok) {
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
      if (logRes.ok) {
        const { count } = await logRes.json();
        assert(count);
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      }
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    }
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  }
};
```

`/api/users/:_id/logs` への `GET` リクエストは、全エクササイズの `log` の配列が追加されたユーザーオブジェクトを返します。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded'
    },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  })
  if(res.ok){
    const {_id, username} = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if(addRes.ok){
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
      if(logRes.ok) {
        const {log} = await logRes.json();
        assert.isArray(log);
        assert.equal(1, log.length);
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      }
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    };
  } else {
    throw new Error(`${res.status} ${res.statusText}`)
  };
};
```

`GET /api/users/:_id/logs` から返される `log` 配列内の各アイテムは、`description`、`duration` および `date` プロパティを持つオブジェクトです。

```js
async () => {
  const url = code;
  const res = await fetch(url + `/api/users`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded'
    },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if(res.ok) {
    const {_id, username} = await res.json();
     const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if(addRes.ok) {
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
      if(logRes.ok) {
        const {log} = await logRes.json();
        const exercise = log[0];
        assert.exists(exercise);
        assert.exists(exercise.description);
        assert.exists(exercise.duration);
        assert.exists(exercise.date);
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      };
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    };
  } else {
    throw new Error(`${res.status} ${res.statusText}`)
  };
};
```

`GET /api/users/:_id/logs` から返される `log` 配列内のどのオブジェクトの `description` プロパティも、文字列である必要があります。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded',
    },
    body: `username=fcc_test_${Date.now()}`.substring(0,29)
  });
  if(res.ok) {
    const {_id, username} = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/x-www-form-urlencoded',
      },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if(addRes.ok) {
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
      if(logRes.ok){
        const {log} = await logRes.json();
        const exercise = log[0];
        assert.isString(exercise.description);
        assert.equal(exercise.description, expected.description);
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      }
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    };
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  };
};
```

`GET /api/users/:_id/logs` から返される `log` 配列内のどのオブジェクトの `duration` プロパティも、数値である必要があります。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded',
    },
    body: `username=fcc_test_${Date.now()}`.substring(0,29)
  });
  if(res.ok) {
    const {_id, username} = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/x-www-form-urlencoded',
      },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if(addRes.ok) {
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
      if(logRes.ok){
        const {log} = await logRes.json();
        const exercise = log[0];
        assert.isNumber(exercise.duration);
        assert.equal(exercise.duration, expected.duration);
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      }
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    };
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  };
};
```

`GET /api/users/:_id/logs` から返される `log` 配列内のどのオブジェクトの `date` プロパティも、文字列である必要があります。 `Date` API の `dateString` 形式を使用してください。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded',
    },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });

  if (res.ok) {
    const { _id, username } = await res.json();
    const currentDate = new Date();
    const expectedDates = [
      new Date(currentDate.setDate(currentDate.getDate() - 1)).toLocaleDateString("en-US", {
        timeZone: "UTC", weekday: "short", month: "short",
        day: "2-digit", year: "numeric"
      }).replaceAll(',', ''),
      new Date().toLocaleDateString("en-US", {
        timeZone: "UTC", weekday: "short", month: "short",
        day: "2-digit", year: "numeric"
      }).replaceAll(',', ''),
      new Date(currentDate.setDate(currentDate.getDate() + 1)).toLocaleDateString("en-US", {
        timeZone: "UTC", weekday: "short", month: "short",
        day: "2-digit", year: "numeric"
      }).replaceAll(',', '')
    ];
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
    };
    const addRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/x-www-form-urlencoded',
      },
      body: `description=${expected.description}&duration=${expected.duration}`
    });
    if (addRes.ok) {
      const logRes = await fetch(url + `/api/users/${_id}/logs`);
      if (logRes.ok) {
        const { log } = await logRes.json();
        const exercise = log[0];
        assert.isString(exercise.date);
        assert.include(expectedDates, exercise.date); // Check if date matches any valid dates
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      }
    } else {
      throw new Error(`${addRes.status} ${addRes.statusText}`);
    };
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  };
};
```

`GET /api/users/:_id/logs` リクエストに `from`、`to` および `limit` パラメーターを追加すると、任意のユーザーについてログの一部を取得できます。 `from` および `to` は、`yyyy-mm-dd` 形式の日付です。 `limit` は、返されるログの数を表す整数です。

```js
async () => {
  const url = code;
  const res = await fetch(url + '/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: `username=fcc_test_${Date.now()}`.substring(0, 29)
  });
  if (res.ok) {
    const { _id, username } = await res.json();
    const expected = {
      username,
      description: 'test',
      duration: 60,
      _id,
      date: new Date().toDateString()
    };
    const addExerciseRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}&date=1990-01-01`
    });
    const addExerciseTwoRes = await fetch(url + `/api/users/${_id}/exercises`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: `description=${expected.description}&duration=${expected.duration}&date=1990-01-03`
    });
    if (addExerciseRes.ok && addExerciseTwoRes.ok) {
      const logRes = await fetch(
        url + `/api/users/${_id}/logs?from=1989-12-31&to=1990-01-04`
      );
      if (logRes.ok) {
        const { log } = await logRes.json();
        assert.isArray(log);
        assert.equal(2, log.length);
      } else {
        throw new Error(`${logRes.status} ${logRes.statusText}`);
      }
      const limitRes = await fetch(
        url + `/api/users/${_id}/logs?limit=1`
      );
      if (limitRes.ok) {
        const { log } = await limitRes.json();
        assert.isArray(log);
        assert.equal(1, log.length);
      } else {
        throw new Error(`${limitRes.status} ${limitRes.statusText}`);
      }
      const filterDateBeforeLimitRes = await fetch(
        url + `/api/users/${_id}/logs?from=1990-01-02&to=1990-01-04&limit=1`
      );
      if (filterDateBeforeLimitRes.ok) {
        const { log } = await filterDateBeforeLimitRes.json();
        assert.isArray(log);
        assert.equal(1, log.length);
      } else {
        throw new Error(`${filterDateBeforeLimitRes.status} ${filterDateBeforeLimitRes.statusText}`);
      }
    } else {
      throw new Error(`${res.status} ${res.statusText}`);
    }
  } else {
    throw new Error(`${res.status} ${res.statusText}`);
  }
};
```
