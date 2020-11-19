<template>
    <div>
    |<input type="text" class="todo-input" placeholder="Escribe tu tarea" v-model="newTodo" @keyup.enter= "addTodo">
        <div v-for="(todo, index) in todos" :key="todo.id" class="todo-item" >
        
            <div>
                {{todo.title}}
            </div>

            <div class="delete-item" @click="deleteTodo(index)">
            
                &times;
            </div>

            

        </div>
        

    </div>
  
</template>


<script>

import Todo from './Todo.vue';

export default {
    name:"todoList",

    data(){
        return{
            newTodo:'',

            idForTodo:3,

            todos:[
                {
                    'id' : 1,
                    'title': 'primer tarea', 
                    'completed':false,
                    },

                {
                     'id' : 2,
                    'title': 'second task', 
                    'completed':false,

                },
            ],


            
            

            
        }
        
    },
    methods: {

        
                addTodo () {
                    if (this.newTodo.trim().length == 0 ) {
                        
                            return
            
                    }    

                    this.todos.push({
                        id : this.idForTodo,
                        title: this.newTodo,
                        completed:false,



                    })
                    this.newTodo='',
                    this.idForTodo ++
                },
 
                deleteTodo(index){
                    this.todos.splice(index, 1)
                },

                completeItem(){

                }

            },
    
    
    }
</script>

<style >
.todo-item{
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
 .todo-input{
     width: 100%;
     padding: 10px 15px;
     font-size: 18px;
     margin-bottom: 20px;
 }
 .delete-item{
     cursor: pointer;
     margin-left: 14px;
     
 }
 

</style>