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
  - [Actualizamos "src/main.js"](#actualizamos-srcmainjs)
  - [Actualizamos "src/app.vue"](#actualizamos-srcappvue-1)
  - [Realizamos un commit](#realizamos-un-commit-3)
- [Instalación de json-server](#instalación-de-json-server)
  - [Instalamos json-server](#instalamos-json-server)
  - [Creamos "server/db.json"](#creamos-serverdbjson)
  - [Creamos "server/routes.json"](#creamos-serverroutesjson)
- [Ejecución de json-server](#ejecución-de-json-server)
  - [Ejecutamos json-server desde nuestro directorio base](#ejecutamos-json-server-desde-nuestro-directorio-base)
  - [Visualizamos la ruta en nuestro navegador](#visualizamos-la-ruta-en-nuestro-navegador)
  - [Realizamos un commit](#realizamos-un-commit-4)
- [Creacion de los environments](#creacion-de-los-environments)
  - [Creamos ".env.development"](#creamos-envdevelopment)
  - [Creamos ".env.test"](#creamos-envtest)
  - [Creamos ".env.production"](#creamos-envproduction)
  - [Realizamos un commit](#realizamos-un-commit-5)
- [Creacion de instancia axios](#creacion-de-instancia-axios)
  - [Crear "src/shared/services/http-common.js"](#crear-srcsharedserviceshttp-commonjs)
  - [Realizamos un commit](#realizamos-un-commit-6)
- [Crearcion de entitdad "Tutorial"](#crearcion-de-entitdad-tutorial)
  - [Crear "src/learning/model/tutorial.entity.js"](#crear-srclearningmodeltutorialentityjs)
  - [Realizamos un commit](#realizamos-un-commit-7)
- [Creacion del servicio "Tutorials"](#creacion-del-servicio-tutorials)
  - [Crear "src/learning/services/tutorials-api.service.js"](#crear-srclearningservicestutorials-apiservicejs)
  - [Realizamos un commit](#realizamos-un-commit-8)


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

![](resources/2024-04-24_20-23-32.png)

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

``` js
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

![](resources/2024-04-24_20-27-52.png)

## Actualizamos "src/main.js"

``` js
import { createApp } from 'vue'
import './style.css'
import App from './app.vue'

// Import router
import router from "./router/index.js";

// PrimeVue
import PrimeVue from 'primevue/config';

// PrimeVue CSS
import 'primeflex/primeflex.css';

// PrimeVue Icons
import 'primeicons/primeicons.css';

// PrimeVue Material Design Theme
import 'primevue/resources/themes/mdc-light-indigo/theme.css';

// PrimeVue Services
import ToastService         from 'primevue/toastservice';
import ConfirmationService  from "primevue/confirmationservice";
import DialogService        from "primevue/dialogservice";

// PrimeVue Components
import DataTable        from "primevue/datatable";
import Column           from "primevue/column";
import ConfirmDialog    from "primevue/confirmdialog";
import Row              from "primevue/row";
import Toolbar          from "primevue/toolbar";
import InputText        from "primevue/inputtext";
import Textarea         from "primevue/textarea";
import Button           from "primevue/button";
import Sidebar          from "primevue/sidebar";
import Menu             from "primevue/menu";
import Dialog           from "primevue/dialog";
import Toast            from "primevue/toast";
import Dropdown         from "primevue/dropdown";
import Tag              from "primevue/tag";
import Card             from "primevue/card";
import FileUpload       from "primevue/fileupload";
import IconField        from "primevue/iconfield";
import InputIcon        from "primevue/inputicon";
import InputNumber      from "primevue/inputnumber";
import FloatLabel       from "primevue/floatlabel";
import Checkbox         from "primevue/checkbox";
import Rating           from "primevue/rating";

createApp(App)
    .use(router)
    .use(PrimeVue, { ripple: true })
    .use(DialogService)
    .use(ConfirmationService)
    .use(ToastService)
    .component('pv-button',         Button)
    .component('pv-card',           Card)
    .component('pv-column',         Column)
    .component('pv-confirm-dialog', ConfirmDialog)
    .component('pv-checkbox',       Checkbox)
    .component('pv-data-table',     DataTable)
    .component('pv-dialog',         Dialog)
    .component('pv-dropdown',       Dropdown)
    .component('pv-file-upload',    FileUpload)
    .component('pv-float-label',    FloatLabel)
    .component('pv-icon-field',     IconField)
    .component('pv-input-icon',     InputIcon)
    .component('pv-input-text',     InputText)
    .component('pv-input-number',   InputNumber)
    .component('pv-menu',           Menu)
    .component('pv-rating',         Rating)
    .component('pv-row',            Row)
    .component('pv-sidebar',        Sidebar)
    .component('pv-tag',            Tag)
    .component('pv-textarea',       Textarea)
    .component('pv-toolbar',        Toolbar)
    .component('pv-toast',          Toast)
    .mount('#app')
```

![](resources/2024-04-24_20-28-55.png)

## Actualizamos "src/app.vue"

``` vue
<script>
export default {
  name: "app",
  title: "ACME Learning Center",

  data() {
    return {
      drawer: false,
      items: [
        {label: 'Home', to: '/home'},
        {label: 'About', to: '/about'},
      ]
    }
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    },

  }
}
</script>

<template>
  <pv-toast></pv-toast>
  <header>
    <pv-toolbar class="bg-primary" fixed>
      <template #start>
        <pv-button class="p-button-text text-white" icon="pi pi-bars" @click="toggleDrawer()"></pv-button>
        <h3>ACME Learning Center</h3>

        <div class="flex-column">
          <router-link v-for="item in items" :key="item.label" v-slot="{ navigate, href}" :to="item.to" custom>
            <pv-button :href="href" class="p-button-text text-white" @click="navigate">
              {{ item.label }}
            </pv-button>
          </router-link>
        </div>
      </template>
    </pv-toolbar>
  </header>
  <pv-sidebar v-model:visible="drawer"></pv-sidebar>
  <router-view></router-view>
</template>

<style scoped>
</style>
```

![](resources/2024-04-24_20-30-44.png)

## Realizamos un commit

``` bash
git add .
git commit -m "feat(in-app-navigation): added in-app navigation initial routes."
```

![](resources/2024-04-24_20-39-09.png)
![](resources/2024-04-24_20-39-19.png)

# Instalación de json-server

## Instalamos json-server

``` bash
npm i -g json-server@0.17.4
```

![](resources/2024-04-24_20-41-31.png)

## Creamos "server/db.json"

``` json
{
  "tutorials": [
    {
      "id": 1,
      "title": "The Vue Tutorials",
      "description": "The best tips and tutorials for Vue.",
      "published": false,
      "status": "Unpublished"
    },
    {
      "id": 2,
      "title": "Amazing Microsoft .NET",
      "description": "Weekly tutorials about .NET and ASP.NET Core.",
      "published": false
    },
    {
      "id": 3,
      "title": "JavaScript for All",
      "description": "Tips and tricks about JavaScript from scratch.",
      "published": false
    },
    {
      "id": 4,
      "title": "Vue Unleashed",
      "description": "Vue at its best.",
      "published": false
    },
    {
      "id": 5,
      "title": "ASP.NET Code Advanced",
      "description": "What nobody tells you about ASP.NET Core.",
      "published": true,
      "status": "Published"
    },
    {
      "id": 6,
      "title": "The Vue Zone",
      "description": "Incredible articles about Vue",
      "published": false,
      "status": "Unpublished"
    }
  ]
}
```

![](resources/2024-04-24_20-42-37.png)

## Creamos "server/routes.json"

``` json
{
  "/api/v1/*": "/$1"
}
```

![](resources/2024-04-24_20-43-49.png)

# Ejecución de json-server

## Ejecutamos json-server desde nuestro directorio base

``` bash
cd server
json-server --watch db.json --routes routes.json -p 3000
```

![](resources/2024-04-24_21-02-41.png)
![](resources/2024-04-24_20-45-49.png)

## Visualizamos la ruta en nuestro navegador 

![](resources/2024-04-24_20-50-10.png)

## Realizamos un commit

``` bash
git add .
git commit -m "chore(server): added json-server configuration files."
```

![](resources/2024-04-24_20-51-38.png)

# Creacion de los environments

## Creamos ".env.development"

``` bash
VITE_API_BASE_URL="http://localhost:3000/api/v1"
```

![](resources/2024-04-24_21-07-16.png)

## Creamos ".env.test"

``` bash
VITE_API_BASE_URL="http://localhost:3000/api/v1"
```

![](resources/2024-04-24_21-07-25.png)

## Creamos ".env.production"

``` bash
VITE_API_BASE_URL="http://localhost:3000/api/v1"
```

![](resources/2024-04-24_21-07-33.png)

## Realizamos un commit

``` bash
git add .
git commit -m "chore: added environments to project."
```

![](resources/2024-04-24_21-08-37.png)
![](resources/2024-04-24_21-09-03.png)

# Creacion de instancia axios

## Crear "src/shared/services/http-common.js"

``` js
/**  axios default configs */
import axios from "axios";

const API_BASE_URL = import.meta.env.VITE_API_BASE_URL;

/**
 * Axios instance
 * @summary http axios instance creation with default configs
 * @type {AxiosInstance}
 *
 */

const http = axios.create({
    baseURL: API_BASE_URL,
    headers: { 'Content-type': 'application/json' }
});

export default http;
```

![](resources/2024-04-24_21-11-32.png)

## Realizamos un commit

``` bash
git add .
git commit -m "feat(acme-service-client): added axios common instance with default configuration."
```

![](resources/2024-04-24_21-12-04.png)
![](resources/2024-04-24_21-12-20.png)

# Crearcion de entitdad "Tutorial"

## Crear "src/learning/model/tutorial.entity.js"

``` js
/**
 * Tutorial
 * @description Tutorial entity
 */
export class Tutorial {
    constructor(id, title, description, published) {
        this.id = id;
        this.title = title;
        this.description = description;
        this.published = published;
        this.status = this.published === true ? 'Published' : 'Unpublished';
    }

    /**
     * Create a new Tutorial instance from a displayableTutorial
     * @param displayableTutorial - The displayableTutorial to create the Tutorial from
     * @returns {Tutorial}
     */
    static fromDisplayableTutorial(displayableTutorial) {
        return new Tutorial(
            displayableTutorial.id,
            displayableTutorial.title,
            displayableTutorial.description,
            displayableTutorial.status.label === 'Published');
    }

    /**
     * Convert a tutorial to a displayable tutorial
     * @param tutorial - The tutorial to convert
     * @returns {{description: *, id, title, status: (string)}}
     */
    static toDisplayableTutorial(tutorial) {
        return {
            id: tutorial.id,
            title: tutorial.title,
            description: tutorial.description,
            status: tutorial.published === true ? 'Published' : 'Unpublished'
        };
    }

}
```

## Realizamos un commit

``` bash
git add .
git commit -m "feat(tutorials): added tutorial entity."
```

![](resources/2024-04-24_21-14-23.png)
![](resources/2024-04-24_21-14-54.png)

# Creacion del servicio "Tutorials"

## Crear "src/learning/services/tutorials-api.service.js"

``` js
import http from "../../shared/services/http-common.js";

/**
 * TutorialsApiService class
 * @description Service class for making HTTP requests to the API
 */

export class TutorialsApiService {
    /**
     * Get all tutorials
     * @returns {Promise<axios.AxiosResponse<any>>}
     */
    getAll() {
        return http.get('/tutorials');
    }

    /**
     * Get tutorial by id
     * @param id
     * @returns {Promise<axios.AxiosResponse<any>>}
     */
    getById(id) {
        return http.get(`/tutorials/${id}`);
    }

    /**
     * Create a new tutorial
     * @param tutorialResource - tutorial object to create
     * @returns {Promise<axios.AxiosResponse<any>>}
     */
    create(tutorialResource) {
        return http.post('/tutorials', tutorialResource);
    }

    /**
     * Update a tutorial
     * @param id - tutorial id to update
     * @param tutorialResource - tutorial object with data
     * @returns {Promise<axios.AxiosResponse<any>>}
     */
    update(id, tutorialResource) {
        return http.put(`/tutorials/${id}`, tutorialResource);
    }

    /**
     * Delete a tutorial
     * @param id - tutorial id to delete
     * @returns {Promise<axios.AxiosResponse<any>>}
     */
    delete(id) {
        return http.delete(`/tutorials/${id}`);
    }

    /**
     * Delete all tutorials that match the given title
     * @param title - tutorial title to apply as criteria
     * @returns {Promise<axios.AxiosResponse<any>>}
     */
    findByTitle(title) {
        return http.get(`/tutorials?title=${title}`);
    }
}
```

![](resources/2024-04-24_21-16-52.png)

## Realizamos un commit

``` bash
git add .
git commit -m "feat(tutorials): added tutorials service."
```
