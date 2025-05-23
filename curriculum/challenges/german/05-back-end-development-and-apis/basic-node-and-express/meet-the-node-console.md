---
id: 587d7fb0367417b2b2512bed
title: Lerne Node console kennen
challengeType: 2
forumTopicId: 301515
dashedName: meet-the-node-console
---

# --description--

Working on these challenges will involve you writing your code using one of the following methods:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-express/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete these challenges locally.
- Benutze einen Website-Builder deiner Wahl, um das Projekt abzuschließen. Achte darauf, alle Dateien von unserem GitHub-Repo zu integrieren.

During the development process, it is important to be able to check what’s going on in your code.

Node is just a JavaScript environment. Like client side JavaScript, you can use the console to display useful debug information. On your local machine, you would see console output in a terminal.

We recommend to keep the terminal open while working at these challenges. By reading the output in the terminal, you can see any errors that may occur.

Der Server muss neu gestartet werden, nachdem Änderungen an seinen Dateien vorgenommen wurden.

You can stop the server from the terminal using `Ctrl + C` and start it using Node directly (`node mainEntryFile.js`) or using a run script in the `package.json` file with `npm run`.

Das `"start": "node server.js"`-Skript kann zum Beispiel mit `npm run start` vom Terminal aus gestartet werden.

To implement server auto restarting on file save Node provides the `--watch` flag you can add to your start script `"start": "node --watch server.js"` or you can install an npm package like `nodemon`. Wir überlassen es dir, dies zu üben.

# --instructions--

Ändern Sie die Datei `myApp.js`, um "Hello World" auf der Konsole zu protokollieren.

# --hints--

`"Hello World"` should be in the console

```js
  $.get(code + '/_api/hello-console').then(
    (data) => {
      assert.isTrue(data.passed, '"Hello World" is not in the server console');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

