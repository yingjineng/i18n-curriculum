---
id: 587d8248367417b2b2512c3c
title: Pide a los navegadores que accedan a tu sitio a través de HTTPS sólo con helmet.hsts()
challengeType: 2
forumTopicId: 301573
dashedName: ask-browsers-to-access-your-site-via-https-only-with-helmet-hsts
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

HTTP Strict Transport Security (HSTS) es una política de seguridad web que ayuda a proteger a los sitios web contra ataques de degradación de protocolo y secuestro de cookies. Si se puede acceder a tu sitio web a través de HTTPS, puedes pedirle a los navegadores de los usuarios que eviten el uso de HTTP inseguro. Al configurar el encabezado Strict-Transport-Security, le dices a los navegadores que usen HTTPS para las solicitudes futuras en un período de tiempo específico. Esto funcionará para las solicitudes que vengan después de la solicitud inicial.

# --instructions--

Configura `helmet.hsts()` para usar HTTPS durante los próximos 90 días. Pasa el objeto de configuración `{maxAge: timeInSeconds, force: true}`. Puedes crear una variable `ninetyDaysInSeconds = 90*24*60*60;` para usar con `timeInSeconds`.

Nota: Configurar HTTPS en un sitio web personalizado requiere la adquisición de un dominio, y un certificado SSL/TLS.

# --hints--

el middleware helmet.hsts() debe ser montado correctamente

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'hsts');
      assert.property(data.headers, 'strict-transport-security');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

maxAge debe ser igual a 7776000 s (90 días)

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.match(
        data.headers['strict-transport-security'],
        /^max-age=7776000;?/
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

