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

            <div class="checkbox__important">
                <input 
                    type='checkbox' 
                    id="important"
                    v-model='newTask.important' />
                <label
                    for="important"> ważne </label>
            </div>

            <button @click="addTask" class="button__add">
                dodaj zadanie
            </button>

            <ul v-for="task in tasks" v-bind:key="task.id" class="ul__tasks" >
                <li v-if="task.important == true" class='task--important'>{{ task.title }}</li>
                <li v-else class='task--nonImportant'>{{ task.title }}</li>
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
        tasks: [{
            title: 'Umyć auto',
            category: 'inne',
            id: Math.random(),
            important: false,
            completed: false
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
        if(this.newTask.title !== ''){
            this.tasks.push(this.newTask);
        }
        
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

        padding: 20px;
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
        user-select: none;
    }

    .select__category{
        width: 100%;
        text-align: center;
    }

    .select__category select{
        padding: 2px 5px;
        text-align: center;
        cursor: pointer;
        border: 1px solid black;
        user-select: none;
    }

    .checkbox__important{
        margin: 5px;
        font-weight: bold;
        letter-spacing: 2px;
        color: red;
        user-select: none;
    }

    .button__add{
        padding: 5px 10px;
        margin: 15px 0 5px;
        border: 1px solid black;
        box-shadow: 2px 2px 4px 0px rgb(42, 43, 49);
        background-color: transparent;
        cursor: pointer;
        user-select: none;
    }

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