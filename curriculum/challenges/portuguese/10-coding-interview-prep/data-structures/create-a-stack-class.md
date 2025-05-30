---
id: 587d8250367417b2b2512c5f
title: Criar uma classe de pilha
challengeType: 1
forumTopicId: 301633
dashedName: create-a-stack-class
---

# --description--

In the last section, we talked about what a stack is and how we can use an array to represent a stack. In this section, we will be creating our own stack class. Although you can use arrays to create stacks, sometimes it is best to limit the amount of control we have with our stacks. Apart from the `push` and `pop` method, stacks have other useful methods. Let's add a `peek`, `isEmpty`, and `clear` method to our stack class.

# --instructions--

Escreva um método `push`, que insere um elemento no topo da pilha, um método `pop`, que remove e retorna o elemento do topo da pilha, um método `peek`, que examina o elemento que está no topo da pilha, um método `isEmpty`, que verifica se a pilha está vazia, e um método `clear` que remove todos os elementos da pilha. Normalmente pilhas não têm isso, mas nós adicionamos um método auxiliar `print`, que registra no console a coleção.

# --hints--

A classe `Stack` deve ter o método `push`.

```js
assert(
  (function () {
    var test = new Stack();
    return typeof test.push === 'function';
  })()
);
```

A classe `Stack` deve ter o método `pop`.

```js
assert(
  (function () {
    var test = new Stack();
    return typeof test.pop === 'function';
  })()
);
```

A classe `Stack` deve ter o método `peek`.

```js
assert(
  (function () {
    var test = new Stack();
    return typeof test.peek === 'function';
  })()
);
```

A classe `Stack` deve ter o método `isEmpty`.

```js
assert(
  (function () {
    var test = new Stack();
    return typeof test.isEmpty === 'function';
  })()
);
```

A classe `Stack` deve ter o método `clear`.

```js
assert(
  (function () {
    var test = new Stack();
    return typeof test.clear === 'function';
  })()
);
```

O método `peek` deve retornar o elemento do topo da pilha

```js
assert(
  (function () {
    var test = new Stack();
    test.push('CS61');
    test.push('CS50');
    return test.peek() === 'CS50' && test.peek() === 'CS50';
  })()
);
```

O método `pop` deve remover e retornar o elemento do topo da pilha

```js
assert(
  (function () {
    var test = new Stack();
    test.push('CS61');
    test.push('CS50');
    return test.pop() === 'CS50' && test.pop() === 'CS61';
  })()
);
```

O método `isEmpty` deve retornar true se uma pilha não tiver nenhum elemento

```js
assert(
  (function () {
    var test = new Stack();
    return test.isEmpty();
  })()
);
```

O método `clear` deve remover todos os elementos da pilha

```js
assert(
  (function () {
    var test = new Stack();
    test.push('CS61');
    test.push('CS50');
    test.clear();
    return test.isEmpty();
  })()
);
```

# --seed--

## --seed-contents--

```js
function Stack() {
  var collection = [];
  this.print = function() {
    console.log(collection);
  };
  // Only change code below this line

  // Only change code above this line
}
```

# --solutions--

```js
class Stack {
  constructor() {
    this.collection = [];
  }
  print() {
    console.log(this.collection);
  }
  push(val) {
    this.collection.push(val);
  }
  pop() {
    return this.collection.pop();
  }
  peek() {
    return this.collection[this.collection.length - 1];
  }
  isEmpty() {
    return this.collection.length === 0;
  }
  clear() {
    return (this.collection.length = 0);
  }
}
```
