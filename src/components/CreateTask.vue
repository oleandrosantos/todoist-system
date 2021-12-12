<template>
      <div class="container col-md-4 border" id="createTask">
        <label class="form-label fs-5">Tarefa</label>
        <input type="text" class="form-control" placeholder="Digite a sua tarefa" v-model="Task">
        <br/>
        <div class="d-grid gap-4 d-md-flex justify-content-md-end">
          <button class="btn btn-primary me-md-2" v-on:click="addTask">Adicionar</button>
        </div>
      </div>
      <br/>
      <div class="container col-md-4 border" id="createTask">
      <p class="text-center fs-2">Tarefas</p>

      <div class="card">
        <ul class="list-group list-group-flush">
            
            <li class="list-group-item" v-for="task in taskList" :key="task.id">
              <div class="btn-toolbar justify-content-between" role="toolbar" aria-label="Toolbar with button groups">
              <div class="form-check">
               <input class="form-check-input" width="16" height="16" type="checkbox" value="" id="checkInput">
              <label class="form-check-label fs-5" id="checkLabel">
              {{ task}}
              </label>
              </div>
              <div class="btn-group" id="btngroup" role="group">
                <button type="button" class="btn btn-danger" v-on:click="delTask(task.id)"> 
                 <img src="assets/x-square.svg" />
                 </button>
              </div>
              </div>
            </li>

            
        </ul>
      </div>
        
      </div>

</template>

<script>
export default {
  Task: '',
  data(){
    return{
      taskList: []
    }
  },
  methods:{
    addTask(){
      this.taskList.push(this.Task);
      this.Task= '';
    },
    delTask(position){
      this.taskList.splice(position);
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