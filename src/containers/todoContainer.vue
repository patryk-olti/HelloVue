<template>
  <div class="hello">
    <input type="text" placeholder="wprowadź zadanie" v-model="newTask" />

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

    <button>
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
        newTask: '',
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

  }
}
</script>

<style>

</style>