# vuejs_typescript_starter_kit

> A Vue.js/Typescript/Vuex/Webpack starter pack  
> I've basically tried to put together the minimum you need to get started   
> Typescript typing works throughout as far as I can tell, including within single-file VUE components  
> Webpack works great both in dev mode (dev server with auto-reload), and in build mode    

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## One of the two example VUE components is below. A component that abstracts a URL.

```typescript
<template>
  <div class="link">
      <a :href="link.url">{{link.description}}</a>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";
import * as T from "../types/common";

@Component({
  name: "LinkComponent",
  props: {
    url: String,
    description: String
  }
})
export default class cLink extends Vue {
  link: T.Link = { url: "", description: "Link" };

  mounted() {
    this.link.url = this.$props.url || this.link.url;
    this.link.description = this.$props.description || this.link.description;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a {
  color: #42b983;
}
</style>
```
