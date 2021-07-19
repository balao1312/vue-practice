<template>
  <div class="task">
      <h3>{{ task.text }}</h3>
      <p>{{ task.day }}</p>
  </div>
</template>


<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

<style scoped>
.fas {
  color: red;
}
.task {
  background: hsl(200, 100%, 70%);
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task:hover {
  background: hsl(200, 100%, 50%)
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
