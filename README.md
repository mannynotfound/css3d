css3d
========

Wrapper around [three.js](https://github.com/mrdoob/three.js/tree/r58) + [CSS3D Renderer](https://github.com/mrdoob/three.js/blob/dev/examples/js/renderers/CSS3DRenderer.js) + [tween.js](https://github.com/tweenjs/tween.js).

Allows you to easily require all three libraries together with CommonJS or include in your html file as a script tag. The exported class has all the properties of three.js, CSS3D Renderer, and tween.js.

eg:

```js
var CSS3D = require('css3d');

// use three.js
var camera = new CSS3D.PerspectiveCamera(
  75, window.innerWidth / window.innerHeight, 1, 5000
);

// use css3d renderer
var element = document.createElement('div');
var object = new CSS3D.CSS3DObject(element);

// use tween
new CSS3D.TWEEN.Tween(object.position)
  .to({ y: Math.random() * 2000 - 1000 }, 2000)
  .easing(CSS3D.TWEEN.Easing.Exponential.Out)
  .start();
```

or

```html
<html>
  <head>
    <title>CSS3D</title>
  </head>
  <body>
    <div id="container"></div>
    <script type="text/javascript" src="css3d.js"></script>
    <script type="text/javascript">
      var element = document.createElement('div');
      var object = new CSS3D.CSS3DObject(element);
      // ..
    </script>
  </body>
</html>
```
