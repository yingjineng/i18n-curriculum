---
id: 67d301cc87b84eaa42bdcdbe
title: 什么是 tsconfig 文件，以及为什么在 TypeScript 项目中包含它很重要？
challengeType: 11
videoId: H-n6N7zmNCg
dashedName: what-is-a-tsconfig-file-and-why-is-it-important-to-include-in-your-typescript-projects
---

# --description--

观看视频或阅读文字稿并回答下方问题。

# --transcript--

什么是 tsconfig 文件，以及为什么在 TypeScript 项目中包含它很重要？

让我们来了解一下 tsconfig 文件！

TypeScript 的编译器设置可以根据你的项目需求进行配置。这些配置存放在项目根目录下的 `tsconfig.json` 文件中。实际上，如果没有这个文件，编译器将无法运行，除非你直接传递命令行参数。那么，这个文件到底有什么作用呢？让我们来看一个示例文件：

```json
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./prod",
    "lib": ["ES2023"],
    "target": "ES2023",
    "module": "ES2022",
    "moduleResolution": "Node",
    "esModuleInterop": true,
    "skipLibCheck": true,
    "strict": true
  },
  "exclude": ["test/"]
}
```

看起来内容很多！我们来逐项解析。`compilerOptions` 属性包含了配置的“核心”部分——这里可以控制 TypeScript 编译器的行为。来看下这个嵌套对象……

`rootDir` 和 `outDir` 告诉 TypeScript 源代码目录和编译后 JavaScript 代码的输出目录。

`lib` 属性决定编译器使用哪些类型定义，可以为特定的 ES 版本、DOM 等提供支持。

`module` 和 `moduleResolution` 配合使用，管理你的包如何使用模块——可以是 CommonJS 或 ECMAScript。

`esModuleInterop` 允许 CommonJS 和 ES 模块之间更好地互操作，通过自动为导入创建命名空间对象，使你更容易在 TypeScript 项目中混合使用不同模块系统的模块。`skipLibCheck` 选项则跳过对代码中未通过导入引用的 `.d.ts` 文件的类型检查。

最后是 `strict` 模式。可以说，没有启用这个选项，TypeScript 的帮助就大打折扣，因为它会开启许多其他检查，比如要求你正确处理可空类型，或者在 TypeScript 无法推断类型而回退为 any 时发出警告。

最后补充一点，关于顶层的 `exclude` 属性——当你定义了源代码目录后，可能还有一些 TypeScript 代码不在该目录下，而你又不希望它们被编译进生产代码，比如测试代码。`exclude` 数组告诉编译器在编译时忽略这些 TypeScript 文件，但像 Intellisense 这样的工具仍然可以检测到潜在问题。

还有很多其他编译器选项可以探索——超过 50 个！建议你查阅文档并尝试，找到最适合你项目需求的配置。

# --questions--

## --text--

`tsconfig.json` 文件中哪个属性影响编译器的行为？

## --answers--

`rootDir`

### --feedback--

该属性是一个包含编译器选项的对象。

---

`compilerOptions`

---

`exclude`

### --feedback--

该属性是一个包含编译器选项的对象。

---

`lib`

### --feedback--

该属性是一个包含编译器选项的对象。

## --video-solution--

2

## --text--

`tsconfig.json` 文件中的 `strict` 选项有什么作用？

## --answers--

它只检查可空类型。

### --feedback--

该选项会启用多种检查，包括可空类型的处理。

---

它强制使用 CommonJS 模块。

### --feedback--

该选项会启用多种检查，包括可空类型的处理。

---

它切换多项类型检查选项。

---

它将测试文件排除在编译之外。

### --feedback--

该选项会启用多种检查，包括可空类型的处理。

## --video-solution--

3

## --text--

`tsconfig.json` 文件中的 `exclude` 数组有什么作用？

## --answers--

指定要编译的文件。

### --feedback--

你可以用它将测试代码排除在编译之外。

---

列出要包含的额外库。

### --feedback--

你可以用它将测试代码排除在编译之外。

---

在编译时忽略某些文件。

---

定义编译后文件的输出目录。

### --feedback--

你可以用它将测试代码排除在编译之外。

## --video-solution--

3

