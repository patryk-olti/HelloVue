<template>
    <ul v-for="task in tasksArray" v-bind:key="task.id" class="ul__tasks" >
        <li             
            :class="{
                'task--nonImportant': task.important === false,
                'task--hobby': task.category === 'hobby',
                'task--work': task.category === 'praca',
                'task--sport': task.category === 'sport',
                'task--others': task.category === 'inne',
                'task--important': task.important === true,
            }"
        >{{ task.title }}</li>
    </ul>
</template>

<script>
export default {
  name: 'TasksList',
  props: {
      tasksArray: {
          type: Array,
          require: false
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

    .task--nonImportant{
        color: black;
        font-size: 1.2rem;
    }

    .task--hobby{
        color: blue;
    }

    .task--work{
        color: yellow;
    }

    .task--sport{
        background-color: aqua;
    }

    .task--others{
        text-decoration: underline;
    }

    .task--important{
        color: red;
        background-color: transparent;
        font-size: 1.2rem;
    }
    
</style>
