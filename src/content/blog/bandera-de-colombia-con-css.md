---
title: "Crea la bandera de Colombia con HTML y CSS"
description: "El día de hoy les enseñaré como crear la bandera de Colombia usando tan solo HTML y CSS con pocas líneas de código."
pubDate: "Jun 19 2021"
heroImage: "/blog-placeholder-4.jpg"
---

HTML y CSS muchas veces son menos preciados porque no son lenguaje de programación, pero aun así son muy importantes para la web. Con CSS no tan solo se pueden hacer estilos, sino que también se pueden hacer dibujos, ilustraciones, videojuegos, etc. Aquí te dejo un hermoso proyecto de arte con CSS [DibujarteCSS](https://dibujartecss.musarte.dev).

Lo primero que debemos crear es nuestra estructura de **HTML**:

```html
<div class="bandera">Bandera</div>
```

Lo único que debemos poner en nuestro código HTML es un div con una clase para darle los estilos. Ahora vamos a darle los estilos con **CSS**:

```css
.bandera {
  width: 90%;
  max-width: 500px;
  height: 300px;
  box-shadow: 0 150px 0 #f5cb15 inset, 0 225px 0 #00368f inset,
    0 300px 0 #c81125 inset;
}
```

Para crear la bandera con CSS debemos darle estilos a la clase que colocamos anteriormente al div en el HTML y darle un width y un height, para crear los colores de la bandera de Colombia lo haremos usando **sombras**!!. Usaremos tres sombras y el truco es darle un tamaño en Y a las sombras y darle la opción de inset para que la sombra se haga desde el interior. El resultado es el siguiente:

<div className="mb-4">
  <iframe
    className="rounded-md"
    width="100%"
    height="464"
    scrolling="no"
    title="Bandera de Colombia"
    src="https://codepen.io/andresparradev/embed/XWXogMx?default-tab=result"
  ></iframe>
</div>

Si quieres ir al siguiente nivel y mejorar un poco más la bandera de Colombia agregándole animaciones.

```css
@keyframes mover {
  to {
    transform: scale(1.03);
  }
}
.bandera {
  width: 100%;
  max-width: 500px;
  height: 300px;
  box-shadow: 0 150px 0 #f5cb15 inset, 0 225px 0 #00368f inset,
    0 300px 0 #c81125 inset;
  margin: 1rem auto;
  transition: all 0.2s ease;
  animation: mover 0.5s infinite alternate ease-in-out;
}
```

Aquí te dejo una versión de la bandera hecha en [Codepen](https://codepen.io/andresparradev/pen/XWXogMx) para que puedas ver el código completo y jugar con el.
