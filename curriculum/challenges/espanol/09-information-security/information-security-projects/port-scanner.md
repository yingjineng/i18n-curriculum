---
id: 5e46f979ac417301a38fb932
title: Escáner de puertos
challengeType: 10
forumTopicId: 462372
helpCategory: Python
dashedName: port-scanner
---

# --description--

You will be <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-port-scanner" target="_blank" rel="noopener noreferrer nofollow">working on this project with our Gitpod starter code</a>. Learn <a href="https://forum.freecodecamp.org/t/how-to-use-gitpod-in-the-curriculum/668669#how-can-i-share-my-workspace-to-get-help-8" target="_blank" rel="noopener noreferrer nofollow">how to share your Gitpod workspace to get help</a>.

Estamos desarrollando las instrucciones interactivas del currículo de Python. Aunque puedes encontrar los siguientes videos en el canal de YouTube de freeCodeCamp.org que te enseñaran lo necesario para realizar este proyecto:

- <a href="https://www.freecodecamp.org/news/python-for-everybody/" target="_blank" rel="noopener noreferrer nofollow">Python for Everybody Video Course</a> (14 hours)

- <a href="https://www.freecodecamp.org/news/learn-python-basics-in-depth-video-course/" target="_blank" rel="noopener noreferrer nofollow">Aprende la Base de Python a fondo</a> (4 horas)

- <a href="https://www.freecodecamp.org/news/intermediate-python-course/" target="_blank" rel="noopener noreferrer nofollow">Curso Intermedio de Python</a> (6 horas)

# --instructions--

Crear un escáner de puerto usando Python.

En el archivo `port_scanner.py`, crea una función llamada `get_open_ports`, esta tomara un argumento `target` y otro argumento llamado `port_range`. El `target` puede ser un URL o una dirección IP. El `port_range` es un lista de dos numeros, indicando el primer y ultimo numero del rango de los puertos a verificar.

Aquí hay unos ejemplos de como la función debe ser llamada:

```py
get_open_ports("209.216.230.240", [440, 445])
get_open_ports("www.stackoverflow.com", [79, 82])
```

La función debe retornar una lista de puertos abiertos en el rango dado.

La función `get_open_ports` también debería tomar un tercer argumento opcional de `True` para indicar de forma "Detallada". Si este es establecido como verdadero, la función debe retornar una cadena descriptiva en lugar de una lista de puertos.

Este es el formato de la cadena que debe retornarse en modo detallado (el texto dentro de las `{}` indica la información que debe aparecer):

```bash
Open ports for {URL} ({IP address})
PORT     SERVICE
{port}   {service name}
{port}   {service name}
```

Puedes usar el diccionario en `common_ports.py` para obtener el nombre del servicio correcto para cada puerto.

Por ejemplo, si la función es llamada así:

```py
port_scanner.get_open_ports("scanme.nmap.org", [20, 80], True)
```

Esto debe retornar lo siguiente:

```bash
Open ports for scanme.nmap.org (45.33.32.156)
PORT     SERVICE
22       ssh
80       http
```

Asegúrese de incluir el espacio adecuado y los caracteres de la nueva línea.

Si el URL pasado dentro de la función `get_open_ports` es invalido, la función debe retornar la cadena de texto: "Error: Invalid hostname".

Si la dirección IP pasada dentro de la función `get_open_ports` es invalida, la función debe retornar la cadena de texto: "Error: Invalid IP address".

## Desarrollo

Escribe tu codigo en `port_scanner.py`. Para el desarrollo, puedes usar `main.py` para probar tu código.

## Pruebas

Las pruebas unitarias para este proyecto están en `test_module.py`. Importamos las pruebas de `test_module.py` a `main.py` para su comodidad.

## Enviar

Copia la URL de tu proyecto y envíalo a freeCodeCamp.

# --hints--

Debe pasar todas las pruebas de Python.

```js

```

# --solutions--

```py
  # Python challenges don't need solutions,
  # because they would need to be tested against a full working project.
  # Please check our contributing guidelines to learn more.
```
