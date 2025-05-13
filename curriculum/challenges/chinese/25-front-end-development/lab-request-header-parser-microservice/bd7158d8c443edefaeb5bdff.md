---
id: bd7158d8c443edefaeb5bdff
title: 构建请求头解析微服务
challengeType: 4
dashedName: lab-request-header-parser-microservice
---

# --description--

构建一个与此功能类似的全栈 JavaScript 应用：<a href="https://request-header-parser-microservice.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://request-header-parser-microservice.freecodecamp.rocks/</a>。你可以通过以下任一方式编写你的代码来完成本项目：

-   克隆<a href="https://github.com/freeCodeCamp/boilerplate-project-headerparser/" target="_blank" rel="noopener noreferrer nofollow">此 GitHub 仓库</a>并在本地完成你的项目。
-   使用<a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-project-headerparser/" target="_blank" rel="noopener noreferrer nofollow">我们的 Gitpod 初始项目</a>来完成你的项目。
-   使用你选择的网站生成器来完成项目。需要包含我们 GitHub 仓库的所有文件。

# --hints--

你应该提供你自己的项目，而不是示例网址。

```js
(getUserInput) => {
  assert(
    !/.*\/request-header-parser-microservice\.freecodecamp\.rocks/.test(
      getUserInput('url')
    )
  );
};
```

对 `/api/whoami` 的请求应返回一个包含你的 IP 地址的 JSON 对象，键名为 `ipaddress`。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/whoami').then(
    (data) => assert(data.ipaddress && data.ipaddress.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

对 `/api/whoami` 的请求应返回一个包含你的首选语言的 JSON 对象，键名为 `language`。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/whoami').then(
    (data) => assert(data.language && data.language.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

对 `/api/whoami` 的请求应返回一个包含你的软件信息的 JSON 对象，键名为 `software`。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/api/whoami').then(
    (data) => assert(data.software && data.software.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```
