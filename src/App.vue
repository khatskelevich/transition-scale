<template>
  <div class="container">
    <component :is="currentComponent"></component>
  </div>
</template>

<script lang="ts">
import {Options, Vue} from 'vue-class-component'
import Menu from './components/Menu.vue'

@Options({
  components: {
    Menu
  },
})
export default class App extends Vue {
  currentComponent = 'Menu'
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100%;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;

  .container {
    width: 500px;
    height: 500px;
  }
}
</style>
