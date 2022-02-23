<template>
  <form @submit="onSubmit" class="add-form">
      <div class="form-control">
          <label>Note</label>
          <input type="text" name="text" v-model="text" placeholder="add comment">
      </div>
      <div class="form-control">
          <label>Date and time</label>
          <input type="text" name="day" v-model="day" placeholder="date and time">
      </div>
      <div class="from-control form-control-check">
          <label>select</label>
          <input type="checkbox" v-model="reminder" value="reminder">
      </div>
      <input type="submit" value="Save Task" class="btn btn-block">
  </form>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            text: '',
            day: '',
            reminder: false,
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()

            if(!this.text) {
                alert('Please add comment')
                return
            }
            const newTask = {
                id: Math.floor(Math.random() * 100000),
                text: this.text,
                day: this.day,
                reminder: this.reminder,
            }
            this.$emit('add-task', newTask)
            this.text = ''
            this.day = ''
            this.reminder = false
        }
    },
}
</script>

<style scoped>
.add-form {
    margin-bottom: 40px;
}
.form-control label {
    display: block;
}
.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}
.form-control-check {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.form-control-check label {
    flex: 1;
}
.form-control-check label {
    flex: 2;
    height: 20px;
}
.btn-block {
    display: block;
    width: 100%;
}
</style>