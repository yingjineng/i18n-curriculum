---
id: bad87fee1348bd9aedd08845
title: 버튼에 Font Awesome 아이콘 추가하기
challengeType: 0
forumTopicId: 16638
required:
  - 
    link: 'https://use.fontawesome.com/releases/v5.8.1/css/all.css'
    raw: true
dashedName: add-font-awesome-icons-to-our-buttons
---

# --description--

Font Awesome is a convenient library of icons. These icons can be webfonts or vector graphics. These icons are treated just like fonts. You can specify their size using pixels, and they will assume the font size of their parent HTML elements.

Font Awesome은 어떤 앱에서든 사용할 수 있으며, 사용하기 위해서는 HTML 파일의 맨 위에 다음 코드를 삽입하면 됩니다.

```html
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">
```

이번 과제에서는, 저희가 이 코드를 이미 추가해 두었습니다.

`i` 요소는 원래 요소들에 이탤릭체를 주기 위해 사용되었지만, 여기서는 주로 아이콘에 사용됩니다. 다음과 같이 Font Awesome 클래스를 `i` 요소에 추가하여 아이콘을 사용할 수 있습니다.

```html
<i class="fas fa-info-circle"></i>
```

`span`요소 또한 아이콘과 함께 사용할 수 있습니다.

# --instructions--

Font Awesome을 사용해 `thumbs-up`아이콘을 좋아요 버튼에 추가해주세요. `fas`클래스, `fa-thumbs-up`클래스를 가진 `i` 요소를 추가해주시면 됩니다. 아이콘 옆의 `Like`라는 텍스트는 유지돼야 합니다.

# --hints--

`fas`클래스, `fa-thumbs-up` 클래스를 가진 `i` 요소를 추가해주세요.

```js
assert.isTrue(document.querySelector('i')?.classList?.value === 'fas fa-thumbs-up' || document.querySelector('span')?.classList?.value === 'fas fa-thumbs-up');
```

Like 버튼 안에 `fa-thumbs-up`아이콘이 들어있어야 합니다.

```js
const iconTextContent = document.querySelector('i.fa-thumbs-up')?.parentNode?.textContent;  
const spanTextContent = document.querySelector('span.fa-thumbs-up')?.parentNode?.textContent;  
assert.isTrue(
  (iconTextContent?.match(/Like/gi) &&
    document.querySelector('.btn-primary > i') === document.querySelector('.fas.fa-thumbs-up')) ||
    (spanTextContent?.match(/Like/gi) &&
      document.querySelector('.btn-primary > span') === document.querySelector('.fas.fa-thumbs-up')));
```

`i` 요소는 `button` 요소 안에 중첩되어야 합니다.

```js
const button = document.querySelector('button'); 
const i = button?.querySelectorAll("i");
const span =  button?.querySelectorAll("span");
assert(i.length > 0 ||span.length > 0);
```

아이콘 요소에는 닫는 태그가 있어야 합니다.

```js
assert.match(code, /(<\/i>|<\/span>)\s*Like\s*<\/button>/g);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  h2 {
    font-family: Lobster, Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }
</style>

<div class="container-fluid">
  <div class="row">
    <div class="col-xs-8">
      <h2 class="text-primary text-center">CatPhotoApp</h2>
    </div>
    <div class="col-xs-4">
      <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
    </div>
  </div>
  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats <span class="text-danger">love:</span></p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```

# --solutions--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  h2 {
    font-family: Lobster, Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }
</style>

<div class="container-fluid">
  <div class="row">
    <div class="col-xs-8">
      <h2 class="text-primary text-center">CatPhotoApp</h2>
    </div>
    <div class="col-xs-4">
      <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
    </div>
  </div>
  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary"><i class="fas fa-thumbs-up"></i> Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats <span class="text-danger">love:</span></p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```
