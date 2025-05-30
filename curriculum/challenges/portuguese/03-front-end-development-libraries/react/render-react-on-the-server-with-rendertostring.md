---
id: 5a24c314108439a4d403618d
title: Renderizar React no servidor com renderToString
challengeType: 6
forumTopicId: 301407
dashedName: render-react-on-the-server-with-rendertostring
---

# --description--

So far, you have been rendering React components on the client. Normally, this is what you will always do. However, there are some use cases where it makes sense to render a React component on the server. Since React is a JavaScript view library and you can run JavaScript on the server with Node, this is possible. In fact, React provides a `renderToString()` method you can use for this purpose.

Existem duas principais razões pelas quais a renderização no servidor pode ser usada em um aplicativo do mundo real. Primeiro, sem fazer isso, seus aplicativos React consistiriam em um arquivo HTML relativamente vazio e um grande pacote de JavaScript quando inicialmente é carregado ao navegador. Isso pode não ser ideal para motores de busca que estão tentando indexar o conteúdo das suas páginas para que as pessoas possam te encontrar. Se você renderizar a marcação HTML inicial no servidor e enviar para o client, a carga inicial da página contém todas as marcações da página que podem ser rastreadas por motores de busca. Em segundo lugar, isso cria uma experiência de carregamento de página inicial mais rápida, porque o HTML renderizado é menor do que o código JavaScript de todo o aplicativo. React ainda será capaz de reconhecer seu aplicativo e gerenciá-lo após a carga inicial.

# --instructions--

O método `renderToString()` é fornecido em `ReactDOMServer`, que está disponível aqui como um objeto global. O método recebe um argumento que é um elemento React. Use isso para renderizar `App` em uma string.

# --hints--

O componente `App` deve renderizar em uma string usando `ReactDOMServer.renderToString`.

```js
() =>
  assert(
    code.replace(/ /g, '')
      .includes('ReactDOMServer.renderToString(<App/>)') &&
      Enzyme.mount(React.createElement(App)).children().name() === 'div'
  );
```

# --seed--

## --before-user-code--

```jsx
var ReactDOMServer = { renderToString(x) { return null; } };
```

## --after-user-code--

```jsx
ReactDOM.render(<App />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class App extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <div/>
  }
};

// Change code below this line
```

# --solutions--

```jsx
class App extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <div/>
  }
};

// Change code below this line
ReactDOMServer.renderToString(<App/>);
```
