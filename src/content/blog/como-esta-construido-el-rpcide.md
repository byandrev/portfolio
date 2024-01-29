---
title: "Como esta construido el RPCIDE"
description: "Explicación de como está construido el RPCIDE y como funciona, así como los componentes que lo conforman."
pubDate: "Jul 26 2023"
heroImage: "/blog-placeholder-3.jpg"
---

## Introduccion

El RPCIDE es un **IDE** (Integrated Development Environment). Este está construido en diferentes tecnologías, como **React**, **NodeJS**, **Firebase**, **MongoDB** y muchas más.

![Imagen que muestra la arquitectura del RPCIDE](https://firebasestorage.googleapis.com/v0/b/blog-e296e.appspot.com/o/posts%2Frelease-rpcide%2Farchitect.png?alt=media&token=32db72f5-57e0-4b70-8782-e2c42816d502)

### Frontend

El frontend está construido en React con Typescript, utilizando la librería [ChakraUI](https://chakra-ui.com/) la cual nos permite crear componentes de manera rápida y sencilla. Para el editor de código se utiliza la librería [Monaco Editor](https://www.npmjs.com/package/@monaco-editor/react). El frontend está alojado en [Vercel](https://vercel.com).

### Backend

En el backend se utiliza NodeJS con Typescript, utilizando Express como framework para el servidor. El backend está alojado en [Vercel](https://vercel.com).

Para el manejo de la base de datos se utiliza [Firestore](https://firebase.google.com/docs/firestore), la cual es una base de datos NoSQL que nos ofrece [Firebase](https://firebase.google.com/). Este nos ofrece un limite gratuito que es más que suficiente para el uso que se le da en el RPCIDE.

Para la ejecución de los archivos se utiliza la [Codex API](https://github.com/Jaagrav/CodeX-API), la cual es una API que nos permite ejecutar código de diferentes lenguajes de programación utilizando Docker y NodeJS. Tenemos un fork de la API en [Fork Codex API](https://github.com/rpcide/CodeX-API) y está desplegado en [fly.io](https://fly.io). Este fork se mejorará con el tiempo para que se adapte de mejor manera a las necesidades del RPCIDE.

Se utiliza [Pino](https://github.com/pinojs/pino-http) como logger para el backend y [logtail](https://betterstack.com/logs) para visualizar los logs.
