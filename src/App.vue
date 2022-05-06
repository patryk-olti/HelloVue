<template>
  <div>
    <HelloWorld />
    <todoContainer />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import todoContainer from './containers/todoContainer.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    todoContainer
  }
}
</script>

<style>

</style>
