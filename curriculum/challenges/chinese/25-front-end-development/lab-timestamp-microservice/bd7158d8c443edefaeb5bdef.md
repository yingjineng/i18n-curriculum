---
id: bd7158d8c443edefaeb5bdef
title: 构建一个时间戳微服务
challengeType: 4
dashedName: lab-timestamp-microservice
---

# --description--

构建一个与此功能类似的全栈 JavaScript 应用：<a href="https://timestamp-microservice.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://timestamp-microservice.freecodecamp.rocks</a>。你可以通过以下任一方式编写你的代码来完成本实验：

-   克隆<a href="https://github.com/freeCodeCamp/boilerplate-project-timestamp/"  target="_blank" rel="noopener noreferrer nofollow">此 GitHub 仓库</a>并在本地完成你的项目。
-   使用<a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-project-timestamp/"  target="_blank" rel="noopener noreferrer nofollow">我们的 Gitpod 启动项目</a>来完成你的项目。
-   使用你选择的网站生成器来完成项目。需要包含我们 GitHub 仓库的所有文件。

**注意：** 本项目不涉及时区转换，因此所有有效日期都假定用 `new Date()` 以 GMT 解析。

# --hints--

提交你自己的项目，而不是示例的 URL。

```js
(getUserInput) => {
  assert(
    !/.*\/timestamp-microservice\.freecodecamp\.rocks/.test(getUserInput('url'))
  );
};
```

向 `/api/:date?` 发送一个带有有效日期的请求，应该返回一个 JSON 对象，其中 `unix` 键是输入日期的 Unix 时间戳（以毫秒为单位，类型为 Number）。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/2016-12-25').then(
    (data) => {
      assert.equal(
        data.unix,
        1482624000000,
        '应该是有效的 unix 时间戳'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

向 `/api/:date?` 发送一个带有有效日期的请求，应该返回一个 JSON 对象，其中 `utc` 键包含如 `Thu, 01 Jan 1970 00:00:00 GMT` 格式的输入日期。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/2016-12-25').then(
    (data) => {
      assert.equal(
        data.utc,
        'Sun, 25 Dec 2016 00:00:00 GMT',
        '应该是有效的 UTC 日期字符串'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

向 `/api/1451001600000` 发送请求，应该返回 `{ unix: 1451001600000, utc: "Fri, 25 Dec 2015 00:00:00 GMT" }`。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/1451001600000').then(
    (data) => {
      assert(
        data.unix === 1451001600000 &&
          data.utc === 'Fri, 25 Dec 2015 00:00:00 GMT'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

程序能成功处理能被 `new Date(date_string)` 解析的日期。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/05 October 2011, GMT').then(
    (data) => {
      assert(
        data.unix === 1317772800000 &&
          data.utc === 'Wed, 05 Oct 2011 00:00:00 GMT'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

如果输入的日期字符串无效，API 应返回结构为 `{ error : "Invalid Date" }` 的对象。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/this-is-not-a-date').then(
    (data) => {
      assert.equal(data.error.toLowerCase(), 'invalid date');
    },
    (xhr) => {
      assert(xhr.responseJSON.error.toLowerCase() === 'invalid date');
    }
  );
```

如果传入的参数是空日期，应返回一个包含当前时间 `unix` 键的 JSON 对象。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api').then(
    (data) => {
      var now = Date.now();
      assert.approximately(data.unix, now, 20000);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

如果传入的参数是空日期，应返回一个包含当前时间 `utc` 键的 JSON 对象。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api').then(
    (data) => {
      var now = Date.now();
      var serverTime = new Date(data.utc).getTime();
      assert.approximately(serverTime, now, 20000);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```
