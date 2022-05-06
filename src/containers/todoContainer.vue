<template>
  <div class="hello">
    <input type="text" placeholder="wprowadź zadanie" v-model="newTask.title" />

    <div>
        <ul v-for='category in categories' v-bind:key='category'>
            <li>
                <input type='checkbox' id='category'>
                <label for='category' >{{ category }}</label>
            </li>
        </ul>
    </div>

    <div>
        <input type='checkbox' v-model='newTask.important' />
        <label> ważne </label>
    </div>

    <button @click="addTask">
        dodaj zadanie
    </button>

    <ul v-for="task in tasks" v-bind:key="task.id">
        <li>{{ task.title }}</li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'todoContainer',
  data(){
      return{
        categories: ['hobby', 'praca', 'sport', 'inne'],
        tasks: [{
            id: 1,
            title: 'trening',
            category: 'sport'
        },{
            id: 2,
            title: 'nauka Vue',
            category: 'hobby'
        }],
        newTask: {
            title: '',
            category: 'inne',
            id: Math.random(),
            important: false,
            completed: false
        },
      }
  },
  methods: {
      addTask(){
        console.log('hello: ', this.newTask);
        this.tasks.push(this.newTask);
        
        this.newTask = {
            title: '',
            category: 'inne',
            id: Math.random(),
            important: false,
            completed: false
        }
      }
  }
}
</script>

<style>

</style>