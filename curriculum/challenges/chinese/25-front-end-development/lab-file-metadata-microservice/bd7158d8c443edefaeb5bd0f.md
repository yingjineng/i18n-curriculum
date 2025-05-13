---
id: bd7158d8c443edefaeb5bd0f
title: 文件元数据微服务
challengeType: 4
dashedName: file-metadata-microservice
---

# --description--

构建一个与此功能类似的全栈 JavaScript 应用：<a href="https://file-metadata-microservice.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://file-metadata-microservice.freecodecamp.rocks</a>。你可以通过以下任一方式编写你的代码来完成本实验：

-   克隆<a href="https://github.com/freeCodeCamp/boilerplate-project-filemetadata/" target="_blank" rel="noopener noreferrer nofollow">此 GitHub 仓库</a>，并在本地完成你的项目。
-   使用<a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-project-filemetadata/" target="_blank" rel="noopener noreferrer nofollow">我们的 Gitpod 启动项目</a>来完成你的项目。
-   使用你选择的网站生成器来完成项目。需要包含我们 GitHub 仓库中的所有文件。

# --instructions--

**提示：** 你可以使用 `multer` npm 包来处理文件上传。

# --hints--

请提交你自己的项目，而不是示例的 URL。

```js
(getUserInput) => {
  assert(
    !/.*\/file-metadata-microservice\.freecodecamp\.rocks/.test(
      getUserInput('url')
    )
  );
};
```

你可以提交包含文件上传的表单。

```js
async (getUserInput) => {
  const site = await fetch(getUserInput('url'));
  const data = await site.text();
  const doc = new DOMParser().parseFromString(data, 'text/html');
  assert(doc.querySelector('input[type="file"]'));
};
```

表单的文件输入字段的 `name` 属性应设置为 `upfile`。

```js
async (getUserInput) => {
  const site = await fetch(getUserInput('url'));
  const data = await site.text();
  const doc = new DOMParser().parseFromString(data, 'text/html');
  assert(doc.querySelector('input[name="upfile"]'));
};
```

当你提交一个文件时，你会在 JSON 响应中收到该文件的 `name`、`type` 和以字节为单位的 `size`。

```js
async (getUserInput) => {
  const formData = new FormData();
  const fileData = await fetch(
    'https://cdn.freecodecamp.org/weather-icons/01d.png'
  );
  const file = await fileData.blob();
  formData.append('upfile', file, 'icon');
  const data = await fetch(getUserInput('url') + '/api/fileanalyse', {
    method: 'POST',
    body: formData
  });
  const parsed = await data.json();
  assert.property(parsed, 'size');
  assert.equal(parsed.name, 'icon');
  assert.equal(parsed.type, 'image/png');
};
```
