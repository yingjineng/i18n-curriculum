---
id: 5a24c314108439a4d4036170
title: Creare un componente con stato
challengeType: 6
forumTopicId: 301391
dashedName: create-a-stateful-component
---

# --description--

One of the most important topics in React is `state`. State consists of any data your application needs to know about, that can change over time. You want your apps to respond to state changes and present an updated UI when necessary. React offers a nice solution for the state management of modern web applications.

Puoi creare lo stato in un componente React dichiarando una proprietà `state` nel `constructor` della classe del componente. Questo inizializza il componente con lo `state` quando viene creato. La proprietà `state` deve essere impostata su un `object` JavaScript. La dichiarazione appare così:

```jsx
this.state = {

}
```

Hai accesso all'oggetto `state` per tutta la vita del tuo componente. Puoi aggiornarlo, farne il rendering (cioè visualizzarlo) nella tua interfaccia utente e passarlo come proprietà ai componenti figli. L'oggetto `state` può essere semplice o complesso in base alle tue necessità. Nota che devi creare un componente di classe estendendo `React.Component` per creare uno `state` di questo tipo.

# --instructions--

C'è un componente nell'editor di codice che sta cercando di renderizzare una proprietà `firstName` dal suo `state`. Tuttavia non c'è uno `state` definito. Inizializza il componente con `state` nel `constructor` e assegna il tuo nome a una proprietà `firstName`.

# --hints--

`StatefulComponent` dovrebbe esistere ed effettuare il render.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    return mockedComponent.find('StatefulComponent').length === 1;
  })()
);
```

`StatefulComponent` dovrebbe fare il render di un `div` e di un elemento `h1`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    return (
      mockedComponent.find('div').length === 1 &&
      mockedComponent.find('h1').length === 1
    );
  })()
);
```

Lo stato di `StatefulComponent` dovrebbe essere inizializzato con una proprietà `firstName` impostata su una stringa.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    const initialState = mockedComponent.state();
    return (
      typeof initialState === 'object' && typeof initialState.firstName === 'string'
    );
  })()
);
```

La proprietà `firstName` nello stato di `StatefulComponent` dovrebbe presentare l'elemento `h1`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    const initialState = mockedComponent.state();
    return mockedComponent.find('h1').text() === initialState.firstName;
  })()
);
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<StatefulComponent />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    // Only change code below this line

    // Only change code above this line
  }
  render() {
    return (
      <div>
        <h1>{this.state.firstName}</h1>
      </div>
    );
  }
};
```

# --solutions--

```jsx
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      firstName: 'freeCodeCamp!'
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.firstName}</h1>
      </div>
    );
  }
};
```
