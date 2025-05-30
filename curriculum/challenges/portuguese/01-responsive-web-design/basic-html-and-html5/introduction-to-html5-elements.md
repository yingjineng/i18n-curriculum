---
id: bad87fee1348bd9aecf08801
title: Conhecer os primeiros elementos do HTML5
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cBkZGpt7'
forumTopicId: 301097
dashedName: introduction-to-html5-elements
---

# --description--

HTML5 introduces more descriptive HTML tags. These include `main`, `header`, `footer`, `nav`, `video`, `article`, `section` and others.

Essas tags conferem uma estrutura descritiva ao seu HTML, tornam seu HTML mais fácil de ler e ajudam com a otimização dos mecanismos de busca (SEO) e com a acessibilidade. A tag `main` do HTML5 ajuda os mecanismos de busca e outros desenvolvedores a encontrar o conteúdo principal de sua página.

Vemos abaixo um exemplo de uso de um elemento `main` com dois elementos filhos dentro dele:

```html
<main> 
  <h1>Hello World</h1>
  <p>Hello Paragraph</p>
</main>
```

**Observação:** muitas das novas tags HTML5 e seus benefícios são abordadas na seção Acessibilidade Aplicada.

# --instructions--

Crie um segundo elemento `p` com o texto de kitty ipsum a seguir: `Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.`

Em seguida, crie um elemento `main` e coloque os dois elementos `p` dentro do elemento `main`.

# --hints--

Você deve ter 2 elementos `p` contendo o texto Kitty Ipsum.

```js
assert.lengthOf(document.querySelectorAll('p'),2);
```

Todos os elementos `p` devem ter uma tag de fechamento.

```js
assert.match(code,/<\/p>/g);
assert.strictEqual(code.match(/<\/p>/g).length,code.match(/<p/g).length);
```

O elemento `p` deve conter as primeiras palavras do texto adicional `kitty ipsum` fornecido.

```js
assert.match(document.querySelectorAll('p')[1].textContent,/Purr\s+jump\s+eat/gi);
```

O código deve ter um elemento `main`.

```js
assert.lengthOf(document.querySelectorAll('main'),1);
```

O elemento `main` deve ter dois elementos de parágrafo como filhos.

```js
const main = document.querySelector('main');
const children = main.querySelectorAll("p"); 
assert.lengthOf(children,2);
```

A tag de abertura `main` deve vir antes da primeira tag de parágrafo.

```js
assert.match(code,(/<main>\s*?<p>/g));
```

A tag de fechamento `main` deve vir depois da segunda tag de fechamento de parágrafo.

```js
assert.match(code,(/<\/p>\s*?<\/main>/g));
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
