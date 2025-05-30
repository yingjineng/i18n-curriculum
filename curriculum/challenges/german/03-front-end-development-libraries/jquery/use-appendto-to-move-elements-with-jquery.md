---
id: bad87fee1348bd9aed608826
title: Verwende appendTo, um Elemente mit jQuery zu verschieben
challengeType: 6
forumTopicId: 18340
dashedName: use-appendto-to-move-elements-with-jquery
---

# --description--

Now let's try moving elements from one `div` to another.

jQuery hat eine Funktion namens `appendTo()`, mit der du HTML-Elemente auswählen und sie an ein anderes Element anhängen kannst.

Wenn wir zum Beispiel `target4` von rechts nach links verschieben wollen, würden wir Folgendes verwenden:

```js
$("#target4").appendTo("#left-well");
```

Verschiebe dein Element `target2` von deinem `left-well` zu deinem `right-well`.

# --hints--

Dein Element `target2` sollte sich nicht innerhalb deines `left-well` befinden.

```js
assert($('#left-well').children('#target2').length === 0);
```

Dein Element `target2` sollte sich innerhalb deines `right-well` befinden.

```js
assert($('#right-well').children('#target2').length > 0);
```

Du solltest nur jQuery verwenden, um diese Elemente zu verschieben.

```js
assert(!code.match(/class.*animated/g));
```

# --seed--

## --seed-contents--

```html
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");
    $("#target1").prop("disabled", true);
    $("#target4").remove();

  });
</script>

<!-- Only change code above this line -->

<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target" id="target1">#target1</button>
        <button class="btn btn-default target" id="target2">#target2</button>
        <button class="btn btn-default target" id="target3">#target3</button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target" id="target4">#target4</button>
        <button class="btn btn-default target" id="target5">#target5</button>
        <button class="btn btn-default target" id="target6">#target6</button>
      </div>
    </div>
  </div>
</div>
```

# --solutions--

```html
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");
    $("#target1").prop("disabled", true);
    $("#target4").remove();
    $("#target2").appendTo("#right-well");
  });
</script>

<!-- Only change code above this line -->

<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target" id="target1">#target1</button>
        <button class="btn btn-default target" id="target2">#target2</button>
        <button class="btn btn-default target" id="target3">#target3</button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target" id="target4">#target4</button>
        <button class="btn btn-default target" id="target5">#target5</button>
        <button class="btn btn-default target" id="target6">#target6</button>
      </div>
    </div>
  </div>
</div>
```
