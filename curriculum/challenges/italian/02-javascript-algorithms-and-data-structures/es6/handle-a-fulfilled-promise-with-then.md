---
id: 5cdafbd72913098997531681
title: Gestire una promise mantenuta con then
challengeType: 1
forumTopicId: 301203
dashedName: handle-a-fulfilled-promise-with-then
---

# --description--

Promises are most useful when you have a process that takes an unknown amount of time in your code (i.e. something asynchronous), often a server request. When you make a server request it takes some amount of time, and after it completes you usually want to do something with the response from the server. This can be achieved by using the `then` method.

```js
Promise.prototype.then(onFulfilled, onRejected)
```

Il metodo `then` pianifica le funzioni di callback per l'eventuale completamento di una Promis, ovvero l'adempimento o il rifiuto. Uno dei gestori `onFulfilled` e `onRejected` sarà eseguito per gestire l'adempimento o il rifiuto della promise corrente. Quando la promise viene soddisfatta con `resolve`, viene richiamato il gestore `onFulfilled`.

```js
myPromise.then(result => {

});
```

`result` comes from the argument given to the `resolve` method.

# --instructions--

Add the `then` method to your promise. Use `result` as the parameter of its callback function and log `result` to the console.

# --hints--

You should call the `then` method on the promise.

```js
assert(
  __helpers.removeWhiteSpace(__helpers.removeJSComments(code)).match(/(makeServerRequest|\))\.then\(/g)
);
```

Your `then` method should have a callback function with `result` as its parameter.

```js
assert(resultIsParameter);
```

You should log `result` to the console.

```js
assert(
  resultIsParameter &&
    __helpers
      .removeWhiteSpace(__helpers.removeJSComments(code))
      .match(/\.then\(.*?result.*?console.log\(result\).*?\)/)
);
```

# --seed--

## --after-user-code--

```js
const resultIsParameter = /\.then\((function\(result\){|result|\(result\)=>)/.test(__helpers.removeWhiteSpace(__helpers.removeJSComments(code)));
```

## --seed-contents--

```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to true to represent a successful response from a server
  let responseFromServer = true;

  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});
```

# --solutions--

```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to true to represent a successful response from a server
  let responseFromServer = true;

  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});

makeServerRequest.then(result => {
  console.log(result);
});
```
