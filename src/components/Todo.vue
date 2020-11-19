<template>
<div>
    <div>
       {{title}}
    </div>

    <div class="delete-item" @click="deleteTodo(index)">
        &times;
    </div>
</div>

</template>

<script>

export default {
  data() {
    
    return ({

    title:this.title ,
    
    components: {
        Todo
    },

    props:[title]
  })
}
}
</script>