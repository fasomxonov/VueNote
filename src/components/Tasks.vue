<template>
  <div :key="task" v-for="task in tasks">
      <Task :task="task" />
  </div>
</template>

<script>
import Task from '@/components/Task'
export default {
    name: 'Tasks',
    components: {
        Task,
    },
    props: {
        tasks: Array
    }
}
</script>

<style>

</style>