<template>
      <CreateTask v-on:addTask='addTask'/>

      <div class="container col-md-4 border" id="createTask">
      <p class="text-center fs-2">Tarefas</p>
      <div class="card" v-if="taskList.length !== 0">
        <ul class="list-group list-group-flush">
            <li id="tasks-list" class="list-group-item" v-for="task in taskList" :key="task.id" v-on:click="console.log('cliquei')">
            <button id="taskbutton">
              <div class="btn-toolbar justify-content-between" role="toolbar" aria-label="Toolbar with button groups">
              <div class="form-check">
              <label class="form-check-label fs-5" id="checkLabel">
              {{ task}}
              </label>
              </div>
              <div class="btn-group" id="btngroup" role="group">
                <button type="button" class="btn btn-danger" v-on:click="delTask(task.id)"> 
                 x
                 </button>
              </div>
              </div>
            </button>
            </li>
        </ul>
      </div>
      <div v-else>
          <p class="fs-6">Ainda não há tarefas cadastradas!</p>
      </div>
      </div>
</template>

<script>
import CreateTask from './CreateTask.vue'

export default {
  taskList: [],

    components:{
      CreateTask
      },

  data(){
    return{
      taskList:[]
    }
  },
  
  methods:{
    delTask(position){
      this.taskList.splice(position, 1);
    },
    addTask(Task){
      this.taskList.push(Task);
    }

    },
  }
</script>

<style>
#tasks-list{
  padding: 0;
}
#taskbutton{
  width: 100%;
  height: 100%;
  border: none;
   display: block;
  cursor: pointer;
}
#taskbutton:hover{
  background-color: rgb(103, 180, 103);
}
</style>