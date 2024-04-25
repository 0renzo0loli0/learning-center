<img src="https://media.dev.to/cdn-cgi/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fi%2Fi0tgmgk76qyfha15i4qv.png"
  width="100%" height=300/>

- [Generacion del proyecto en vite](#generacion-del-proyecto-en-vite)
  - [Abrimos el proyecto](#abrimos-el-proyecto)
  - [Instalamos la base de vite/vue](#instalamos-la-base-de-vitevue)
  - [Inicializamos git](#inicializamos-git)
- [Limpieza del proyecto](#limpieza-del-proyecto)
  - [Eliminamos "public/vite.svg"](#eliminamos-publicvitesvg)
  - [Añadimos "public/acme-logo.svg"](#añadimos-publicacme-logosvg)
  - [Actualizamos "index.html"](#actualizamos-indexhtml)
  - [Renombramos "src/App.vue"](#renombramos-srcappvue)
  - [Actualizamos "src/app.vue"](#actualizamos-srcappvue)
  - [Eliminamos el contenido de "src/styles.css"](#eliminamos-el-contenido-de-srcstylescss)
  - [Eliminamos "src/components/" y "src/assets/"](#eliminamos-srccomponents-y-srcassets)
  - [Realizamos un commit](#realizamos-un-commit)
- [Instalacion de dependencias](#instalacion-de-dependencias)
  - [Instalamos las dependencias base de nuestro proyecto](#instalamos-las-dependencias-base-de-nuestro-proyecto)
  - [Realizamos un commit](#realizamos-un-commit-1)
- [Creacion de componentes publicos (Options API)](#creacion-de-componentes-publicos-options-api)
  - [Creamos componente "src/public/pages/home.component.vue"](#creamos-componente-srcpublicpageshomecomponentvue)
  - [Creamos componente src/public/pages/about.component.vue](#creamos-componente-srcpublicpagesaboutcomponentvue)
  - [Creamos componente src/public/pages/page-not-found.component.vue](#creamos-componente-srcpublicpagespage-not-foundcomponentvue)
  - [Realizamos un commit](#realizamos-un-commit-2)
- [Creacion de rutas](#creacion-de-rutas)
  - [Creamos el archivo "src/router.index.js"](#creamos-el-archivo-srcrouterindexjs)


# Generacion del proyecto en vite

``` bash
npm create vite@latest
```

![](resources/2024-04-24_19-28-57.png)

## Abrimos el proyecto

``` bash
cd learning-center
code .
```

![](resources/2024-04-24_20-16-12.png)

## Instalamos la base de vite/vue

``` bash
npm install 
npm run dev
```

![](resources/2024-04-24_19-34-55.png)

## Inicializamos git

``` bash
git init
```

![](resources/2024-04-24_19-35-41.png)

# Limpieza del proyecto

## Eliminamos "public/vite.svg"

``` bash
rm public/vite.svg
```

## Añadimos "public/acme-logo.svg"

``` bash
curl https://raw.githubusercontent.com/upc-pre-202401-si730-sw56/learning-center-main/main/public/acme-logo.svg?token=GHSAT0AAAAAACQM67FG4RVQKC644WL7GJYSZRJU3FQ -o public/acme-logo.svg
```

![](resources/2024-04-24_20-15-39.png)

## Actualizamos "index.html"

``` html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/acme-logo.svg
" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + Vue</title>
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="/src/main.js"></script>
  </body>
</html>
```

![](resources/2024-04-24_20-12-11.png)

## Renombramos "src/App.vue"

``` bash
mv src/App.vue src/app.vue
```

## Actualizamos "src/app.vue"

``` vue
<script setup>
</script>

<template>
</template>

<style scoped>
</style>
```

## Eliminamos el contenido de "src/styles.css"

![](resources/2024-04-24_19-46-31.png)

## Eliminamos "src/components/" y "src/assets/"

``` bash
rm -r src/components 
rm -r src/assets
```

![](resources/2024-04-24_19-48-21.png)

## Realizamos un commit

``` bash
git add .
git commit -m "chore: initial commit."
```

![](resources/2024-04-24_19-49-43.png)

# Instalacion de dependencias

## Instalamos las dependencias base de nuestro proyecto

``` bash
npm i primevue primeicons primeflex vue-router axios
```

![](resources/2024-04-24_19-51-56.png)

## Realizamos un commit

``` bash
git add .
git commit -m "chore: added dependendies."
```

![](resources/2024-04-24_19-52-11.png)
![](resources/2024-04-24_19-52-23.png)

# Creacion de componentes publicos (Options API)

## Creamos componente "src/public/pages/home.component.vue"

``` vue
<script>
export default {
  name: "home",
  title: "Home"
}
</script>

<template>
  <div class="w-full align-content-center">
    <h1>Home</h1>
    <p>Welcome to ACME Learning Center.</p>
  </div>
</template>
```

![](resources/2024-04-24_20-00-26.png)

## Creamos componente src/public/pages/about.component.vue

``` vue
<script>
export default {
  name: "about",
  title: "About Us"
}
</script>

<template>
  <div class="w-full align-content-center">
    <h1>About us</h1>
    <p>ACME Learning Center is an Education Business Platform, part of ACME Corporation.</p>
  </div>
</template>
```

![](resources/2024-04-24_20-00-40.png)

## Creamos componente src/public/pages/page-not-found.component.vue

``` vue
<script>
export default {
  name: "page-not-found"
}
</script>

<template>
  <div class="w-full align-content-center">
    <h1>Page Not Found</h1>
  </div>
</template>
```

![](resources/2024-04-24_20-00-53.png)

## Realizamos un commit

``` bash
git add .
git commit -m "feat: added public components."
```

![](resources/2024-04-24_20-02-29.png)
![](resources/2024-04-24_20-04-27.png)

# Creacion de rutas

## Creamos el archivo "src/router.index.js"

``` javascript
import {createRouter, createWebHistory} from "vue-router";
import HomeComponent from "../public/pages/home.component.vue";
import AboutComponent from "../public/pages/about.component.vue";
import PageNotFoundComponent from "../public/pages/page-not-found.component.vue";

const router = createRouter({
    history: createWebHistory(),
    routes: [
        { path: '/home', component: HomeComponent, meta: { title: 'Home' }, },
        { path: '/about', component: AboutComponent, meta: { title: 'About us' }, },
        { path: '/:pathMatch(.*)*', component: PageNotFoundComponent },
        { path: '/', redirect: '/home' }
    ]
});

router.beforeEach((to, from, next) => {
    let baseTitle = 'ACME Learning Center';
    document.title = `${ baseTitle } | ${to.meta["title"]}`;
    next();
});
export default router;
```