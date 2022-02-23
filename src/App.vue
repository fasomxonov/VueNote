<template>
  <div class="container">
    <Header title="Track" />
    <Tasks :tasks="tasks" />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Tasks from '@/components/Tasks'
export default {
  name: 'App',
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: []
    }
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
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  background-repeat: 5px;
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