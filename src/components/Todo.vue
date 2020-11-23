<template>
<div class="todo-item">
    <div :class="{completed :todo.completed}">
      <input type="checkbox" v-model="todo.completed "  @click="completeTodo">
          {{title}} 
    </div>
      

<!--button delete-->
    <button  class="delete-item"
          @click="deleteTodo">

        &times;
    </button>

    

</div>

</template>

<script>


export default {
  name: "Todo",
  props: {
        todo: {
          type: Object,
          required: true
          },
          index: {
            type: Number,
            required: true
          }
  },
  data(){
    return{
      'id':this.todo.id,
      'title':this.todo.title,
      'completed':this.todo.completed
    }
  },
  methods:{
    deleteTodo(){
      this.$emit('deletedTodo', this.index)
  },
  completeTodo(){
      this.$emit('completedTodo', this.index)
  },

 
  
  
}
}
</script>

<style scoped>
.completed{
  text-decoration: line-through;
  cursor: pointer;
  color:gray;}
  .todo-item{
      margin-bottom: 12px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  animation-duration: 0.3s;
  }
</style>