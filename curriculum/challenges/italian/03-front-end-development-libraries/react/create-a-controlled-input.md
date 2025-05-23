---
id: 5a24c314108439a4d4036178
title: Creare un input controllato
challengeType: 6
forumTopicId: 301385
dashedName: create-a-controlled-input
---

# --description--

Your application may have more complex interactions between `state` and the rendered UI. For example, form control elements for text input, such as `input` and `textarea`, maintain their own state in the DOM as the user types. With React, you can move this mutable state into a React component's `state`. The user's input becomes part of the application `state`, so React controls the value of that input field. Typically, if you have React components with input fields the user can type into, it will be a controlled input form.

# --instructions--

L'editor di codice ha lo scheletro di un componente chiamato `ControlledInput` per creare un elemento `input` controllato. Lo `state` del componente è già inizializzato con una proprietà `input` che contiene una stringa vuota. Questo valore rappresenta il testo che un utente digita nel campo `input`.

Innanzitutto, crea un metodo chiamato `handleChange()` che abbia un parametro denominato `event`. Quando il metodo viene chiamato, riceve un oggetto `event` che contiene una stringa di testo presa dall'elemento `input`. Puoi accedere a questa stringa con `event.target.value` all'interno del metodo. Aggiorna la proprietà `input` dello `state` del componente con questa nuova stringa.

Nel metodo `render`, crea l'elemento `input` sopra il tag `h4`. Aggiungi un attributo `value` uguale alla proprietà `input` dello `state` del componente. In seguito, aggiungi una proprietà `onChange` al metodo di gestione dell'evento `handleChange()`.

Quando scrivi nella casella di input, quel testo viene elaborato dal metodo `handleChange()`, impostato come proprietà `input` nello `state` locale, e presentato come valore nella casella di `input` della pagina. Il componente `state` è la singola fonte autorevole per quanto riguarda i dati di input.

Ultimo ma non meno importante, non dimenticate di aggiungere i binding necessari nel costruttore.

# --hints--

`ControlledInput` dovrebbe restituire un elemento `div` che contiene un `input` e un tag `p`.

```js
assert(
  Enzyme.mount(React.createElement(ControlledInput))
    .find('div')
    .children()
    .find('input').length === 1 &&
    Enzyme.mount(React.createElement(ControlledInput))
      .find('div')
      .children()
      .find('p').length === 1
);
```

Lo stato di `ControlledInput` dovrebbe essere inizializzato con una proprietà `input` impostata su una stringa vuota.

```js
assert.strictEqual(
  Enzyme.mount(React.createElement(ControlledInput)).state('input'),
  ''
);
```

La digitazione nell'elemento di input dovrebbe aggiornare lo stato e il valore dell'input, e l'elemento `p` dovrebbe mostrare questo stato mentre scrivi.

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(ControlledInput));
  const _1 = () => {
    mockedComponent.setState({ input: '' });
    return waitForIt(() => mockedComponent.state('input'));
  };
  const _2 = () => {
    mockedComponent
      .find('input')
      .simulate('change', { target: { value: 'TestInput' } });
    return waitForIt(() => ({
      state: mockedComponent.state('input'),
      text: mockedComponent.find('p').text(),
      inputVal: mockedComponent.find('input').props().value
    }));
  };
  const before = await _1();
  const after = await _2();
  assert(
    before === '' &&
      after.state === 'TestInput' &&
      after.text === 'TestInput' &&
      after.inputVal === 'TestInput'
  );
};
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<ControlledInput />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    // Change code below this line

    // Change code above this line
  }
  // Change code below this line

  // Change code above this line
  render() {
    return (
      <div>
        { /* Change code below this line */}

        { /* Change code above this line */}
        <h4>Controlled Input:</h4>
        <p>{this.state.input}</p>
      </div>
    );
  }
};
```

# --solutions--

```jsx
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(event) {
    this.setState({
      input: event.target.value
    });
  }
  render() {
    return (
      <div>
        <input
          value={this.state.input}
          onChange={this.handleChange} />
        <h4>Controlled Input:</h4>

        <p>{this.state.input}</p>
      </div>
    );
  }
};
```
