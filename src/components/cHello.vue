<template>
  <div class="hello">
    <h1 v-on:click="onClick">{{this.$store.state.links.length}}</h1>
    <h2 v-on:click="$store.commit('increment')">Essential Links</h2>
    <ul>
      <li v-for="link in this.$store.state.links" :key="link.url"><a :href="link.url">{{link.description}}</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><cLink url="https://www.google.com" description="Google"/></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";
import cLink from "../components/cLink.vue";
import * as T from "../types/common";

@Component({
  components: { cLink }
})
export default class cHello extends Vue {
  onClick(): void {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
