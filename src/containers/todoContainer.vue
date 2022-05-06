<template>
    <div class="container">
        <div class="container--border">
            <input type="text" placeholder="wprowadź zadanie" v-model="newTask.title" class='input__title'/>

            <div class='select__category'>
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
    .container{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .container--border{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        padding: 10px;
        border: 1px solid black;
        border-radius: 5px;
        box-shadow: 6px 6px 10px 0px rgb(42, 43, 49);
    }

    .input__title{
        padding: 5px;
        margin-bottom: 5px;
        font-size: 1rem;

        border: none;
        border-bottom: 1px solid rgb(100, 100, 100);
        text-align: center;
    }

    .select__category{
        width: 100%;
        text-align: center;
    }

    .select__category select{
        padding: 2px 5px;
        text-align: center;
        cursor: pointer;
    }

</style>