---
id: 5e444147903586ffb414c94f
title: Build a Polygon Area Calculator Project
challengeType: 23
forumTopicId: 462363
dashedName: build-a-polygon-area-calculator-project
---

# --description--

In diesem Projekt wirst du mit Hilfe der objektorientierten Programmierung eine `Rectangle`-Klasse und eine `Square`-Klasse erstellen. Die `Square`-Klasse sollte eine Unterklasse von `Rectangle` sein und Methoden und Attribute erben.

## Rechteck-Klasse

Es sollte mit den Attributen `width` und `height` initialisiert werden, wenn ein Rechteck-Objekt erstellt wird. Die Klasse sollte auch die folgenden Methoden beinhalten:

- `set_width`
- `set_height`
- `get_area`: Gibt den Bereich zurück (`width * height`)
- `get_perimeter`: Gibt den Umfang zurück (`2 * width + 2 * height`)
- `get_diagonal`: Gibt die Diagonale zurück (`(width ** 2 + height ** 2) ** .5`)
- `get_picture`: Returns a string that represents the shape using lines of '\*'. The number of lines should be equal to the height and the number of '\*' in each line should be equal to the width. Am Ende jeder Zeile sollte eine neue Zeile (`\n`) stehen. If the width or height is larger than 50, this should return the string: `'Too big for picture.'`.
- `get_amount_inside`: Nimmt eine andere Form (Quadrat oder Rechteck) als Argument. Gibt die Anzahl der Male zurück, die die übergebene Form in die Form passen könnte (ohne Drehungen). Zum Beispiel könnte ein Rechteck mit einer Breite von 4 und einer Höhe von 8 in zwei Quadrate mit 4 Seiten passen.

Additionally, if an instance of a `Rectangle` is represented as a string, it should look like: `'Rectangle(width=5, height=10)'`.

## Quadrat-Klasse

Die `Square`-Klasse sollte eine Unterklasse von `Rectangle` sein. Bei der Erstellung eines `Square`-Objekts wird eine einzelne Seitenlänge angegeben. Die `__init__`-Methode sollte die Seitenlänge in den beiden Attributen `width` und `height` der `Rectangle`-Klasse speichern.

Die `Square`-Klasse sollte auf die Methoden der `Rectangle`-Klasse zugreifen können, aber auch eine `set_side`-Methode enthalten. If an instance of a `Square` is represented as a string, it should look like: `'Square(side=9)'`.

Außerdem sollten die Methoden `set_width` und `set_height` der `Square`-Klasse sowohl die Breite als auch die Höhe festlegen.

## Beispiel für die Verwendung

```py
rect = Rectangle(10, 5)
print(rect.get_area())
rect.set_height(3)
print(rect.get_perimeter())
print(rect)
print(rect.get_picture())

sq = Square(9)
print(sq.get_area())
sq.set_side(4)
print(sq.get_diagonal())
print(sq)
print(sq.get_picture())

rect.set_height(8)
rect.set_width(16)
print(rect.get_amount_inside(sq))
```

Dieser Code sollte zurückgeben:

```bash
50
26
Rectangle(width=10, height=3)
**********
**********
**********

81
5.656854249492381
Square(side=4)
****
****
****
****

8
```

Note: open the browser console with F12 to see a more verbose output of the tests.

# --hints--

Die `Square`-Klasse sollte eine Unterklasse von der `Rectangle`-Klasse sein.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None

    def test_subclass(self):
        actual = issubclass(shape_calculator.Square, shape_calculator.Rectangle)
        expected = True
        self.assertEqual(actual, expected, 'Expected Square class to be a subclass of the Rectangle class.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `Square` class should be a distinct class from the `Rectangle` class.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None    

    def test_distinct_classes(self):
        actual = shape_calculator.Square is not shape_calculator.Rectangle
        expected = True
        self.assertEqual(actual, expected, 'Expected Square class to be a distinct class from the Rectangle class.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

A square object should be an instance of the `Square` class and the `Rectangle` class.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_square_is_square_and_rectangle(self):
        actual = isinstance(self.sq, shape_calculator.Square) and isinstance(self.sq, shape_calculator.Rectangle)
        expected = True
        self.assertEqual(actual, expected, 'Expected square object to be an instance of the Square class and the Rectangle class.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The string representation of `Rectangle(3, 6)` should be `'Rectangle(width=3, height=6)'`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_rectangle_string(self):
        actual = str(self.rect)
        expected = "Rectangle(width=3, height=6)"
        self.assertEqual(actual, expected, 'Expected string representation of rectangle to be "Rectangle(width=3, height=6)"')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The string representation of `Square(5)` should be `'Square(side=5)'`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_square_string(self):
        actual = str(self.sq)
        expected = "Square(side=5)"
        self.assertEqual(actual, expected, 'Expected string representation of square to be "Square(side=5)"')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Rectangle(3, 6).get_area()` sollte `18` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_area(self):
        actual = self.rect.get_area()
        expected = 18
        self.assertEqual(actual, expected, 'Expected area of rectangle to be 18')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Square(5).get_area()` sollte `25` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_area(self):        
        actual = self.sq.get_area()
        expected = 25
        self.assertEqual(actual, expected, 'Expected area of square to be 25')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Rectangle(3, 6).get_perimeter()` sollte `18` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_perimeter(self):
        actual = self.rect.get_perimeter()
        expected = 18
        self.assertEqual(actual, expected, 'Expected perimeter of rectangle to be 18')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Square(5).get_perimeter()` sollte `20` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_perimeter(self):
        actual = self.sq.get_perimeter()
        expected = 20
        self.assertEqual(actual, expected, 'Expected perimeter of square to be 20')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Rectangle(3, 6).get_diagonal()` sollte `6.708203932499369` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_diagonal(self):
        actual = self.rect.get_diagonal()
        expected = 6.708203932499369
        self.assertEqual(actual, expected, 'Expected diagonal of rectangle to be 6.708203932499369')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Square(5).get_diagonal()` sollte `7.0710678118654755` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_diagonal(self):
        actual = self.sq.get_diagonal()
        expected = 7.0710678118654755
        self.assertEqual(actual, expected, 'Expected diagonal of square to be 7.0710678118654755')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

An instance of the `Rectangle` class should have a different string representation after setting new values.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)        

    def test_set_attributes(self):
        self.rect.set_width(7)
        self.rect.set_height(8)        
        actual = str(self.rect)
        expected = "Rectangle(width=7, height=8)"
        self.assertEqual(actual, expected, 'Expected string representation of rectangle after setting new values to be "Rectangle(width=7, height=8)"')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

An instance of the `Square` class should have a different string representation after setting new values by using `.set_side()`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_set_attributes(self):        
        self.sq.set_side(2)        
        actual = str(self.sq)
        expected = "Square(side=2)"
        self.assertEqual(actual, expected, 'Expected string representation of square after setting new values to be "Square(side=2)"')   
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

An instance of the `Square` class should have a different string representation after setting new values by using `.set_width()` or `set_height()`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_set_attributes(self):        
        self.sq.set_height(2)        
        actual = str(self.sq)
        expected = "Square(side=2)"
        self.assertEqual(actual, expected, 'Expected string representation of square after setting new values to be "Square(side=2)"')
        self.sq.set_width(4)
        actual = str(self.sq)
        expected = "Square(side=4)"
        self.assertEqual(actual, expected, 'Expected string representation of square after setting width to be "Square(side=4)"')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `.get_picture()` method should return a different string representation of a `Rectangle` instance.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_rectangle_picture(self):
        self.rect.set_width(7)
        self.rect.set_height(3)
        actual = self.rect.get_picture()
        expected = "*******\\n*******\\n*******\\n"
        self.assertEqual(actual, expected, 'Expected rectangle picture to be different.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `.get_picture()` method should return a different string representation of a `Square` instance.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.sq = shape_calculator.Square(5)

    def test_square_picture(self):
        self.sq.set_side(2)
        actual = self.sq.get_picture()
        expected = "**\\n**\\n"
        self.assertEqual(actual, expected, 'Expected square picture to be different.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `.get_picture()` method should return the string `'Too big for picture.'` if the `width` or `height` attributes are larger than `50`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_big_picture(self):
        self.rect.set_width(51)
        self.rect.set_height(3)
        actual = self.rect.get_picture()
        expected = "Too big for picture."
        self.assertEqual(actual, expected, 'Expected message: "Too big for picture."')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Rectangle(15,10).get_amount_inside(Square(5))` sollte `6` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)
        self.sq = shape_calculator.Square(5)

    def test_get_amount_inside(self):
        self.rect.set_height(10)
        self.rect.set_width(15)
        actual = self.rect.get_amount_inside(self.sq)
        expected = 6
        self.assertEqual(actual, expected, 'Expected "get_amount_inside" to return 6.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Rectangle(4,8).get_amount_inside(Rectangle(3, 6))` sollte `1` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_get_amount_inside_two_rectangles(self):
        rect2 = shape_calculator.Rectangle(4, 8)
        actual = rect2.get_amount_inside(self.rect)
        expected = 1
        self.assertEqual(actual, expected, 'Expected "get_amount_inside" to return 1.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`Rectangle(2,3).get_amount_inside(Rectangle(3, 6))` sollte `0` zurückgeben.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/shape_calculator.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import shape_calculator
from importlib import reload
reload(shape_calculator)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.rect = shape_calculator.Rectangle(3, 6)

    def test_get_amount_inside_none(self):
        rect2 = shape_calculator.Rectangle(2, 3)
        actual = rect2.get_amount_inside(self.rect)
        expected = 0
        self.assertEqual(actual, expected, 'Expected "get_amount_inside" to return 0.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

# --seed--

## --seed-contents--

```py
class Rectangle:
    pass

class Square:
    pass
```

# --solutions--

```py
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def __str__(self):
        return f'Rectangle(width={self.width}, height={self.height})'

    def set_width(self, width):
        self.width = width

    def set_height(self, height):
        self.height = height

    def get_area(self):
        area = self.width * self.height
        return area

    def get_perimeter(self):
        perimeter = self.width * 2 + self.height * 2
        return perimeter

    def get_diagonal(self):
        diagonal = (self.width ** 2 + self.height ** 2) ** 0.5        
        return diagonal

    def get_picture(self):
        if self.width < 50 and self.height < 50:
            picture = f'{"*"*self.width}\n'*self.height            
            return picture
        else:            
            return 'Too big for picture.'

    def get_amount_inside(self, polygon):
        h_number = self.height // polygon.height
        w_number = self.width // polygon.width
        repetition = h_number * w_number        
        return repetition


class Square(Rectangle):
    def __init__(self, side):
        self.width = side
        self.height = side

    def __str__(self):
        return f'Square(side={self.width})'

    def set_width(self, side):
        self.width = side
        self.height = side

    def set_height(self, side):
        self.height = side
        self.width = side

    def set_side(self,side):
        self.width = side
        self.height = side

```
