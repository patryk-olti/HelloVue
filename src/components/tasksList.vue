<template>
    <ul v-for="task in tasksArray" v-bind:key="task.id" class="ul__tasks" >
        <li v-if="task.important == true" class='task--important'>{{ task.title }}</li>
        <li v-else class='task--nonImportant'>{{ task.title }}</li>
    </ul>
</template>

<script>
export default {
  name: 'TasksList',
  props: {
      tasksArray: {
          type: Array,
          require: true
      }
  }
}
</script>

<style scoped>
    .ul__tasks{
        margin: 5px;
        padding: 0;
        list-style-type: none;
    }

    .task--important{
        color: red;
        font-size: 1.2rem;
    }

    .task--nonImportant{
        color: black;
        font-size: 1.2rem;
    }
</style>
