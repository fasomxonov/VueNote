<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" title="Note" :showAddTask="showAddTask" />
    <div v-if="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Tasks from '@/components/Tasks'
import AddTask from '@/components/AddTask'
export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask,
  },
  data() {
    return {
      tasks: [],
      showAddTask: false,
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
    addTask(task) {
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id) {
      if (confirm('Do you want to delete')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'lorem ipsum text 1',
        day: 'lorem ipsum day 1',
        reminder: true,
      },
      {
        id: 2,
        text: 'lorem ipsum text 2',
        day: 'lorem ipsum day 2',
        reminder: true,
      },
      {
        id: 3,
        text: 'lorem ipsum text 3',
        day: 'lorem ipsum day 3',
        reminder: true,
      },
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
  background: rgb(194, 194, 194);
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 2px solid rgb(138, 138, 138);
  border-radius: 10px;
  padding: 30px;
  background-repeat: 5px;
  background: white;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.bnt-block {
  display: block;
  width: 100%;
}
</style>