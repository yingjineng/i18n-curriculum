---
id: 5895f700f9fc0f352b528e63
title: Configura un motor de plantillas
challengeType: 2
forumTopicId: 301564
dashedName: set-up-a-template-engine
---

# --description--

Trabajar en estos desafíos implica escribir tu código usando uno de los siguientes métodos:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-advancednode/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete these challenges locally.
- Usa un constructor de sitios de tu elección para completar el proyecto. Asegúrate de incorporar todos los archivos de nuestro repositorio de GitHub.

Un motor de plantillas te permite utilizar archivos de plantillas estáticas (como los escritos en *Pug*) en tu aplicación. En tiempo de ejecución, el motor de plantillas sustituye las variables de un archivo de plantilla por valores reales que pueden ser suministrados por tu servidor. A continuación, transforma la plantilla en un archivo HTML estático que se envía al cliente. Este enfoque facilita el diseño de una página HTML y permite mostrar variables en la página sin necesidad de realizar una llamada a la API desde el cliente.

`pug@~3.0.0` ya se ha instalado y aparece como dependencia en el archivo `package.json`.

Express necesita saber qué motor de plantillas está utilizando. Utiliza el método `set` para asignar `pug` como valor de la propiedad `view engine`:

```javascript
app.set('view engine', 'pug');
```

Después de eso, añade otro método `set` que establezca la propiedad `views` de tu `app` para que apunte al directorio `./views/pug`. Esto le dice a Express que renderice todas las vistas relativas a ese directorio.

Por último, utiliza `res.render()` en la ruta para tu página de inicio, pasando `index` como primer argumento. Esto mostrará la plantilla `pug`.

Si todo ha ido según lo previsto, la página de inicio de tu aplicación ya no estará en blanco. ¡En su lugar, mostrará un mensaje indicando que has renderizado correctamente la plantilla Pug!

Envía tu página cuando creas que la tienes correcta. If you're running into errors, you can <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#set-up-a-template-engine-1" target="_blank" rel="noopener noreferrer nofollow">check out the project completed up to this point</a>.

# --hints--

Pug debe ser una dependencia.

```js
async () => {
  const url = new URL("/_api/package.json", code);
  const res = await fetch(url);
  const packJson = await res.json();
  assert.property(
    packJson.dependencies,
    'pug',
    'Your project should list "pug" as a dependency'
  );
}
```

El motor de vistas debe ser Pug.

```js
async () => {
  const url = new URL("/_api/app", code);
  const res = await fetch(url);
  const app = await res.json();
  assert.equal(app?.settings?.['view engine'], "pug");
}
```

Debe establecer la propiedad `views` de la aplicación a `./views/pug`.

```js
async () => {
  const url = new URL("/_api/app", code);
  const res = await fetch(url);
  const app = await res.json();
  assert.equal(app?.settings?.views, "./views/pug");
}
```

Utiliza el método de ExpressJS correcto para renderizar la página de índice de la respuesta.

```js
async () => {
  const url = new URL("/", code);
  const res = await fetch(url);
  const data = await res.text();
      assert.match(
        data,
        /FCC Advanced Node and Express/gi,
        'You successfully rendered the Pug template!'
      );
    }
```

Pug debe estar funcionando.

```js
async () => {
  const url = new URL("/", code);
  const res = await fetch(url);
  const data = await res.text();
      assert.match(
        data,
        /pug-success-message/gi,
        'Your projects home page should now be rendered by pug with the projects .pug file unaltered'
      );
    }
```

