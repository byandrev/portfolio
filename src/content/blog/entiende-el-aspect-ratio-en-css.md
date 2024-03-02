---
title: "Entiende el Aspect Ratio en CSS"
description: "Uno de los elementos fundamentales en el diseño de interfaces web es el aspect ratio o relación de aspecto. En pocas palabras, el aspect ratio se refiere a la proporción entre la altura y el ancho de un elemento, este elemento pueden ser imágenes o videos."
pubDate: "Feb 29 2024"
heroImage: "/blog-placeholder-2.jpg"
tags: css,html,web
---

Uno de los elementos fundamentales en el diseño de interfaces web es el **aspect ratio** o **relación de aspecto**. En pocas palabras, el aspect ratio se refiere a la proporción entre la altura y el ancho de un elemento, este elemento pueden ser imágenes o videos.

Algunos de los aspect ratio más conocidos son los siguientes:

![Aspect ratios mas conocidos y usados, 16/9, 1/1 y 9/16](https://firebasestorage.googleapis.com/v0/b/blog-e296e.appspot.com/o/posts%2Faspect-radio-en-css%2F169.png?alt=media&token=3a20deae-5814-40e6-9c2e-da592ddd1cca)

### En CSS

Para definir el aspect ratio de un elemento debes hacer lo siguiente:

```css
selector {
    aspect-ratio: ancho / alto;
}
```

### Mantener el aspect ratio en una imagen

```css
.image {
    width: 100%;
    aspect-ratio: 16 / 9;
}
```

### Accesibilidad

Con el aspect ratio evitamos el [layout shift](https://web.dev/articles/cls), este es algo muy incómodo que suele suceder en los sitios webs. El layout shift hace referencia al movimiento inesperado del contenido de la web cuando los elementos están cargando.

Aquí tienes un ejemplo sin el uso del aspect ratio y otro con esta propiedad, cuando no se usa el botón se traslada cuando carga la imagen, a esto se le llama layout shift.

<video src="https://firebasestorage.googleapis.com/v0/b/blog-e296e.appspot.com/o/posts%2Faspect-radio-en-css%2FAspect%20Ratio%20Article(1).mp4?alt=media&token=c5d36ecb-22ad-4ec9-bdd3-aee7c9c469c7" alt="Video explicando el uso de la propiedad aspect ratio en css" autoplay loop mute></video>


¡Espero que este artículo te haya sido útil para comprender mejor el concepto de aspect ratio en CSS y lo utilizases en tus diseños!