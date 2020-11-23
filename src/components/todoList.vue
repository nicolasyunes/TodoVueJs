<template>
    <div class="container">
    <input type="text" 
        class="todo-input" 
        placeholder="Create the new task" 
        v-model="newTodo" 
        @keyup.enter= "addTodo">
        
        <div  
        >
        <ul>           
            <Todo  
            v-for="(todo, index) in todos" 
            :key="todo.id" 
            class="todo-item"   
            :title="todo.title"    
            @completedTodo="completeTodo"
            @deletedTodo="deleteTodo"
            :todo="todo"  :index="index" /> <!--componente Todo con sus metodos-->
            
        </ul>
            
        
        </div>
        

    </div>
  
</template>


<script>


import Todo from './Todo.vue';

export default {
    name:"todoList",
      components: {
    Todo,
    
  },

    data(){
        return{
            newTodo:'',

            idForTodo:3,

            todos:[
                {
                    'id' : 1,
                    'title': 'first task', 
                    'completed': false
                    },

                {
                     'id' : 2,
                    'title': 'second task', 
                    'completed': false

                }
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
                        completed:false  ,



                    }),
                    
                    this.newTodo='',
                    this.idForTodo ++
                },
                deleteTodo(index){
                    console.log("asdasdasdas")
                   if(this.todos[index].completed === false){

                        if (confirm("estas seguro?")){
                            this.todos.splice(index,1)
                        }
                    }
                    else {
                            
                            this.todos.splice(index,1)
                    }
                },
                completeTodo(index){
                    this.todos[index].completed = !this.todos[index].completed;
                    
                }

                

            },
            
    

            
    }
</script>


<style >
.container{
  margin-bottom: 16px;

}
.todo-item{
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color:Green;
}
 .todo-input{
     width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;
 }
 .delete-item{
   
  cursor: pointer;
  margin-left: 14px;
 }
 .delete-item  :hover {
    color: black;
 }

     
 

</style>