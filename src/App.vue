<template>
  <div class="container">
    <Header title="Task"/>
    <AddTask @add-task="addTask" />
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
  </div>  
  
</template>

<script>

import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'
export default {
  name: 'App',
  components: {
    Header,Tasks,AddTask
  },
  data(){
    return{
      tasks:[]
    }
  },
  methods:{
    deleteTask(id){
      this.tasks = this.tasks.filter((task)=> task.id !== id)
    },
    toggleReminder(id){
      this.tasks = this.tasks.map((task) => 
        task.id === id ? {...task, reminder: !task.
        reminder } : task
      )
    },
    addTask(task){
      this.tasks = [...this.tasks,task]
    }
  },
  created(){
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'March 1st at 1:30pm',
        reminder: true,
      },
      {
        id: 2,
        text: 'Meeting at school',
        day: 'March 2nd at 2:30pm',
        reminder: false,
      },
      {
        id: 3,
        text: 'Food Shopping',
        day: 'March 3rd at 3:30pm',
        reminder: true,
      },
      {
        id: 4,
        text: 'Coding',
        day: 'March 4th at 4:30pm',
        reminder: true,
      }
    ]
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
