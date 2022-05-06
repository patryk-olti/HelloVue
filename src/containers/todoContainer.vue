<template>
  <div class="hello">
    <input type="text" placeholder="wprowadź zadanie" v-model="newTask.title" />

    <div>
        <select 
            name='categories' 
            id='categories' 
            v-model='newTask.category' 
        >
            <option 
                v-for='category in categories' :value='category'
                v-bind:key='category'    
            >
                {{ category }}
            </option>  
        </select>
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
        tasks: [],
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