<template>
    <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label class="task-label">Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add A Task" />
    </div>
    <div class="form-control">
      <label class="day-time-label">Day & Time</label>
      <input type="text" v-model="day" name="day" placeholder="Add A Day & Time" />
    </div>
    <div class="form-control form-control-check">
      <label class="reminder-label">Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
    export default {
        name: 'AddTask',
        data () {
            return {
                text: '',
                day: '',
                reminder: false
            }
        },
        methods: {
            onSubmit(e) {
                e.preventDefault()

                if (!this.text) {
                    alert ('No Task Added.')
                    return
                }

                const newTask = {
                    text: this.text,
                    day: this.day,
                    reminder: this.reminder
                }

                this.$emit('add-task', newTask)

                this.text = ''
                this.day = ''
                this.reminder = false
            }
        }
    }
</script>

<style scoped>

.add-form {
  margin-bottom: 40px;
}

.form-control {
  margin: 20px 0;
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
  padding-right: 90px;
  align-items: center;
  justify-content: space-between;
}

.form-control-check label {
  flex: 1;
}

.form-control-check input {
  flex: 2;
  height: 20px;
}

.task-label{
    padding-left: 10px;
}

.day-time-label{
    padding-left: 10px;
}

.reminder-label{
    padding-left: 10px;
}

.btn{
    background-color:#000;
    color: antiquewhite;
}

.btn:hover {
    background-color: cornflowerblue;
}
</style>