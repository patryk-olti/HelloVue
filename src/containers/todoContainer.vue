<template>
  <div class="hello">
    <input type="text" placeholder="wprowadź zadanie" v-model="newTask.title" />

    <div>
        <ul>
            <li>
                <input type='checkbox'>
                <label> hobby </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> praca </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> sport </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> obowiązki </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> inne </label>
            </li>
        </ul>
    </div>

    <div>
        <input type='checkbox' />
        <label> ważne </label>
    </div>

    <button @click="helloClick">
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
        newTask: {
            title: '',
            category: 'inne',
            id: Math.random(),
            important: false,
            completed: false
        },
        tasks: [{
            id: 1,
            title: 'trening',
            category: 'sport'
        },{
            id: 2,
            title: 'nauka Vue',
            category: 'hobby'
        },
        ]
      }
  },
  methods: {
      helloClick(){
          console.log('hello: ', this.newTask);
          this.newTask = '';
      }
  }
}
</script>

<style>

</style>