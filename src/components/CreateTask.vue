<template>
      <div class="container col-md-4 border" id="createTask">
        <label class="form-label fs-5">Tarefa</label>
        <input type="text" class="form-control" placeholder="Digite a sua tarefa" v-model="Task">
        <br/>
        <div class="d-grid gap-4 d-md-flex justify-content-md-end">
          <button class="btn btn-primary me-md-2" @click="addTask">Adicionar</button>
        </div>
      </div>
      <br/>
</template>

<script>
export default {
  data(){
    return {
      Task: [],
    }
  },
  methods:{
    
    addTask(){
      if(this.Task !== ""){
        this.$emit('addTask', this.Task)
      }
      
      this.Task = "";
    }
  }

}
</script>
<style>
#createTask{
  padding: 1rem;
}
input[type="radio"] {
    display: table-cell;
    vertical-align: middle
}
#icon{
  width: 16px;
  height: 16px;
}
</style>