---
id: 587d7dbc367417b2b2512bae
title: Crea una batería electrónica
challengeType: 3
forumTopicId: 301370
dashedName: build-a-drum-machine
---

# --description--
**Note:** **React 18 has known incompatibilities with the tests for this project (see [issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922))**

**Objetivo:** Construir una aplicación que sea funcionalmente similar a ésta: <a href="https://drum-machine.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://drum-machine.freecodecamp.rocks/</a>.

Completa las siguientes historias de usuario y consigue que todas las pruebas sean aprobadas. Utilice las bibliotecas o API que necesite. Dale tu estilo personal.

Puedes utilizar cualquier combinición de HTML, JavaScript, CSS, Bootstrap, SASS, React, Redux, y jQuery para completar este proyecto. Debes usar un framework de frontend (por ejemplo React), ya que esta sección es sobre el aprendizaje de este tipo de frameworks. No se recomienda utilizar tecnologías adicionales que no hayan sido mencionadas, su uso corre bajo tu propio riesgo. Estamos considerando soportar otros frameworks frontend como Angular y Vue, pero actualmente no les estamos dando soporte. Aceptaremos e intentaremos solucionar todos los reportes de problemas que utilicen el conjunto de tecnologías sugerido para este proyecto. ¡Feliz programación!

**Historia de usuario #1:** Debe ser capaz de ver un contenedor externo con un correspondiente `id="drum-machine"` que contiene todos los demás elementos.

**Historia de usuario #2:** Dentro de `#drum-machine` puedo ver un elemento con un `id="display"` correspondiente.

**Historia de usuario #3:** Dentro de `#drum-machine` puedo ver 9 elementos de drum pad en los que se puede hacer clic, cada uno con un nombre de clase de `drum-pad`, un id único que describe el clip de audio que el pad de tambor será configurado para activar, y un texto interno que corresponde a una de las siguientes teclas del teclado: `Q`, `W`, `E`, `A`, `S`, `D`, `Z`, `X`, `C`. Los pads de la batería DEBEN estar en este orden.

**Historia de usuario #4:** Dentro de cada `.drum-pad`, debe haber un elemento HTML5 `audio` que tenga un atributo `src` apuntando a un clip de audio, un nombre de clase `clip`, y un id correspondiente al texto interno de su padre `.drum-pad` (e.g. `id="Q"`, `id="W"`, `id="E"` etc.).

**Historia de usuario #5:** Cuando hago clic en `.drum-pad` elemento, el clip de audio contenido en su elemento hijo `audio` debe ser activado.

**Historia de usuario #6:** Cuando presione la tecla de activación asociada con cada `.drum-pad`, el clip de audio contenido en su elemento hijo `audio` debe ser activado (p. ej. pulsando la tecla `Q` debería activar el tambor que contiene la cadena `Q`, pulsando la tecla `W` debería activar la tecla Tambor que contiene la cadena `W`, etc.).

**Historia de usuario #7:** Cuando es un `.drum-pad` es activado, una cadena que describe el clip de audio asociado se muestra como el texto interior del elemento `#display` (cada cadena debe ser única).

Aquí tienes algunas muestras de audio que puedes usar para tu batería electrónica:

- [Heater 1](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-1.mp3)
- [Heater 2](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-2.mp3)
- [Heater 3](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-3.mp3)
- [Heater 4](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-4_1.mp3)
- [Clap](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-6.mp3)
- [Open-HH](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Dsc_Oh.mp3)
- [Kick-n'-Hat](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Kick_n_Hat.mp3)
- [Kick](https://cdn.freecodecamp.org/testable-projects-fcc/audio/RP4_KICK_1.mp3)
- [Closed-HH](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Cev_H2.mp3)

Puedes crear tu proyecto <a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">usando esta plantilla de CodePen</a> y dando clic en `Save` para crear la tuya. If you prefer to use another environment, then put this `<script>` tag into the body of your `index.html` file: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

Una vez que hayas terminado, envía la URL de tu proyecto funcional con todos los tests aprobados.

# --solutions--

```js
// solution required
```
