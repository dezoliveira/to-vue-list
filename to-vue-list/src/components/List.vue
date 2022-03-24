<template>
  <div class="container">
    <h1 class="text-center m-4">To Vue List</h1>

    <div class="d-flex m-4">
      <input v-model="task" type="text" placeholder="Enter Task" class="form-control rounded-0">
      <button @click="submitTask" class="btn btn-success rounded-0">Submit</button>
    </div>

    <!-- Table Bootstrap -->
    <table class="table">
    <thead>
      <tr>
        <th scope="col">Task</th>
        <th scope="col">Status</th>
        <th scope="col" class="text-center">#</th>
        <th scope="col" class="text-center">#</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(task, index) in tasks" :key="index">
        <td>{{task.name}}</td>
        <td>{{task.status}}</td>
        <td>
          <div class="text-center" @click="editTask(index)">
            <span>
              <i class="fa fa-pen"></i>
            </span>
          </div>
        </td>
        <td>
          <div class="text-center" @click="deleteTask(index)">
            <span>
              <i class="fa fa-trash"></i>
            </span>
          </div>
        </td>
      </tr>
    </tbody>
  </table>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data(){
    return{
      task: '',
      editedTask: null,
      tasks: [
        {
          name: 'Steal banana from the store',
          status: 'to-do',
        },
        {
          name: 'Eat 1kg of chocolate',
          status: 'in-progress'
        }
      ]
    }
  },

  methods: {
    submitTask(){
      if(this.task.length === 0) return;

      if(this.editedTask === null){
        this.tasks.push({
          name: this.task,
          status: 'to-do'
        })
      }else{
        this.tasks[this.editedTask].name = this.task
        this.editedTask = null
      }

      this.task = ''
    },

    deleteTask(index){
      this.tasks.splice(index, 1)
    },

    editTask(index){
      this.task = this.tasks[index].name
      this.editedTask = index
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .form-control:focus {
  border-color: green;
  -webkit-box-shadow: none;
  box-shadow: none;
}
</style>
