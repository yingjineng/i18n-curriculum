---
id: 64a674c27a7d00f97013ed14
videoId: rIO5326FgPE
title: The Box Model Lesson M
challengeType: 15
dashedName: the-box-model-lesson-m
--- 
# --description--

Because the box model concept is so incredibly fundamental, let’s dig a bit deeper with <a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#what_is_the_css_box_model" target="_blank">this lesson from MDN</a>. It covers the same material as the video above and will introduce you to inline boxes that we will explore in the next lesson. Achten Sie auf die Beispiele und nehmen Sie sich die Zeit, mit ihrem Browser-Editor zu experimentieren!

# --questions--

## --text--

Wie legst du das alternative Box-Modell für alle deine Elemente fest?

## --answers--

```css
html {
    box-sizing: inherit;
}
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

---

```css
* {
    box-sizing: border-box;
}
```

---

```css
html {
  box-sizing: border-box;
}
* {
  box-sizing: inherit;
}
```

---

```css
html {
    box-sizing: border-box;
}
*,
*::before,
*::after {
    box-sizing: inherit;
}
```



## --video-solution--

4
