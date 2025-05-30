---
id: 5a24c314108439a4d4036161
title: Aprender sobre tags JSX com fechamento automático
challengeType: 6
forumTopicId: 301396
dashedName: learn-about-self-closing-jsx-tags
---

# --description--

So far, you’ve seen how JSX differs from HTML in a key way with the use of `className` vs. `class` for defining HTML classes.

Outra forma importante em que o JSX difere do HTML é na ideia da tag de fechamento automático.

Em HTML, quase todas as tags possuem uma tag de abertura e fechamento: `<div></div>`; a tag de fechamento sempre tem uma barra para frente antes do nome da tag que está fechando. However, there are special instances in HTML called <dfn>void elements</dfn>, or elements that don’t require both an opening and closing tag before another element can start.

Por exemplo, a tag de quebra de linha pode ser escrita como `<br>` ou como `<br />`, mas nunca deve ser escrita como `<br></br>`, uma vez que não contém nenhum conteúdo.

Em JSX, as regras são um pouco diferentes. Qualquer elemento JSX pode ser escrito com uma tag de fechamento automático, e todo elemento deve ser fechado. A tag de quebra de linha, por exemplo, deve sempre ser escrita como `<br />` para ser JSX válido que pode ser transpilado. Um `<div>`, por outro lado, pode ser escrito como `<div />` ou `<div></div>`. A diferença é que na primeira versão de sintaxe não há como incluir nada no `<div />`. Você verá em desafios posteriores que essa sintaxe é útil ao renderizar componentes React.

# --instructions--

Corrija os erros no editor de código para que ele seja JSX válido e transpilado com sucesso. Certifique-se de não alterar nenhum conteúdo - você só precisa fechar as tags onde elas são necessárias.

# --hints--

A constante `JSX` deve retornar um elemento `div`.

```js
assert.strictEqual(JSX.type, 'div');
```

A `div` deve conter uma tag `br`.

```js
assert(Enzyme.shallow(JSX).find('br').length === 1);
```

A `div` deve conter uma tag `hr`.

```js
assert(Enzyme.shallow(JSX).find('hr').length === 1);
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(JSX, document.getElementById('root'))
```

## --seed-contents--

```jsx
const JSX = (
  <div>
    <h2>Welcome to React!</h2> <br >
    <p>Be sure to close all tags!</p>
    <hr >
  </div>
);
```

# --solutions--

```jsx
const JSX = (
<div>
  <h2>Welcome to React!</h2> <br />
  <p>Be sure to close all tags!</p>
  <hr />
</div>
);
```
