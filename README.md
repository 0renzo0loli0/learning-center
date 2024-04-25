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