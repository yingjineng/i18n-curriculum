---
id: 5a24c314108439a4d403616a
title: Pasa un arreglo como "props"
challengeType: 6
forumTopicId: 301401
dashedName: pass-an-array-as-props
---

# --description--

El último desafío demostró cómo pasar información desde un componente padre a un componente hijo como `props` o propiedades. Este desafío busca demostrar cómo se pueden pasar arreglos como `props`. Para pasar un arreglo a un elemento JSX, debe ser tratado como JavaScript y envolverlo entre llaves.

```jsx
<ParentComponent>
  <ChildComponent colors={["green", "blue", "red"]} />
</ParentComponent>
```

El componente hijo entonces tiene acceso a la propiedad del arreglo `colors`. Los métodos de arreglo, como `join()` pueden ser usados al acceder a la propiedad.

```jsx
const ChildComponent = (props) => <p>{props.colors.join(', ')}</p>
```

Esto unirá todos los miembros del arreglo `colors` en un string separado por comas: `<p>green, blue, red</p>`. Más adelante veremos otras formas muy comunes en React de renderizar arreglos de datos.

# --instructions--

En el editor de código están definidos los componentes `List` y `ToDo`. Para renderizar cada `List` del componente `ToDo`, pasa una propiedad `tasks` asignada a un arreglo de tareas pendientes, por ejemplo `["walk dog", "workout"]`. Después accede a dicho arreglo `tasks` en el componente `List`, mostrando su valor dentro del elemento `p`. Usa `join(", ")` para mostrar el arreglo `props.tasks` en el elemento `p` como una lista separada por comas. La lista de hoy debe tener al menos 2 tareas y la de mañana por lo menos 3.

# --hints--

El componente `ToDo` debe devolver un solo `div` externo.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return mockedComponent.children().first().type() === 'div';
  })()
);
```

El tercer descendiente del componente `ToDo` debe ser una instancia del componente `List`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return mockedComponent.children().first().childAt(2).name() === 'List';
  })()
);
```

El quinto descendiente del componente `ToDo` debe ser una instancia del componente `List`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return mockedComponent.children().first().childAt(4).name() === 'List';
  })()
);
```

Ambas instancias del componente `List` deben tener una propiedad llamada `tasks` de tipo arreglo.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return (
      Array.isArray(mockedComponent.find('List').get(0).props.tasks) &&
      Array.isArray(mockedComponent.find('List').get(1).props.tasks)
    );
  })()
);
```

El primer componente `List` representando las tareas de hoy debe tener 2 o más miembros.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return mockedComponent.find('List').get(0).props.tasks.length >= 2;
  })()
);
```

El segundo componente `List` representando las tareas de mañana debe tener 3 o más componentes.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return mockedComponent.find('List').get(1).props.tasks.length >= 3;
  })()
);
```

El componente `List` debe renderizar el valor de la propiedad `tasks` en el tag `p`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ToDo));
    return (
      mockedComponent
        .find('p')
        .get(0)
        .props.children.replace(/\s*,\s*/g, ',') ===
        mockedComponent
          .find('List')
          .get(0)
          .props.tasks.join(',')
          .replace(/\s*,\s*/g, ',') &&
      mockedComponent
        .find('p')
        .get(1)
        .props.children.replace(/\s*,\s*/g, ',') ===
        mockedComponent
          .find('List')
          .get(1)
          .props.tasks.join(',')
          .replace(/\s*,\s*/g, ',')
    );
  })()
);
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<ToDo />, document.getElementById('root'))
```

## --seed-contents--

```jsx
const List = (props) => {
  { /* Change code below this line */ }
  return <p>{}</p>
  { /* Change code above this line */ }
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        { /* Change code below this line */ }
        <List/>
        <h2>Tomorrow</h2>
        <List/>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```

# --solutions--

```jsx
const List= (props) => {
  return <p>{props.tasks.join(', ')}</p>
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        <List tasks={['study', 'exercise']} />
        <h2>Tomorrow</h2>
        <List tasks={['call Sam', 'grocery shopping', 'order tickets']} />
      </div>
    );
  }
};
```
