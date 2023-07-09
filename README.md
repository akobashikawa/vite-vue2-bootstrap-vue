# vite-vue2-bootstrap-vue

- `npm create vite@latest vite-vue2-bootstrap-vue`
- `cd vite-vue2-bootstrap-vue`
- `npm install`
- `npm run dev`
- http://localhost:5173/

- `npm install --save vue@2`
- `npm uninstall --save @vitejs/plugin-vue vue@3`
- `npm install --save  @vitejs/plugin-vue2`
- `npm install --save vue-router@3.5.1`
- `npm install --save bootstrap-vue bootstrap@4.3.1`

```js
// vite.config.js

import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue2'
import { fileURLToPath, URL } from 'node:url'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    }
  }
})
```

```js
// src\main.js

// import { createApp } from 'vue'
import Vue from "vue";
import router from "./router";
import './style.css'
import App from './App.vue'

/*--------------------REGISTER BOOTSTRAP---------------------------------*/
import { BootstrapVue, IconsPlugin } from "bootstrap-vue";
// Import Bootstrap an BootstrapVue CSS files (order is important)
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
// Make BootstrapVue available throughout your project
Vue.use(BootstrapVue);
// Optionally install the BootstrapVue icon components plugin
Vue.use(IconsPlugin);
/*-----------------------------------------------------------------------*/

// createApp(App).mount('#app')
new Vue({
  router,
  render: (h) => h(App),
}).$mount("#app");

```
