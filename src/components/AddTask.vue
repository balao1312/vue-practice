<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add Day & Time"
      />
    </div>
    <div class="form-control form-control-check">
      <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        alert("Please input some task.");
        return;
      }

      const newTask = {
        // automatic added by json-server
        // id: Math.floor(Math.random() * 1000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.text = "";
      this.day = "";
      this.reminder = "";

      console.log(`Adding new task ${newTask}`);
      this.$emit("add-task", newTask);
    },
  },
};
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
  margin: 5px;
  /* background-color: hsl(150, 100%, 50%); */
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 0px 10px;
  font-size: 18px;
}
.form-control-check {
  display: flex;
  /* flex-direction: column; */
  align-items: center;
  justify-content: center;
  /* background-color: hsl(150, 100%, 50%); */
}
.form-control-check label {
  flex: 10;
}
.form-control-check input {
  flex: 1;
  height: 30px;
}
</style>
