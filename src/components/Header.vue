<template>
  <header>
    <h1>{{ title }}</h1>
    <div>
      <Button
        v-show="isHomePage"
        @btn-click="$emit('toggle-filter')"
        :color="filtered ? 'orange' : 'purple'"
        :text="`reminder filtered: ${filtered}`"
      />
        <!-- :text="`filtered: ${filtered}`" -->
      <Button
        v-show="isHomePage"
        @btn-click="$emit('toggle-add-task')"
        :color="showAddTask ? 'red' : 'green'"
        :text="showAddTask ? 'Close' : 'Add Task'"
      />
    </div>
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
    filtered: Boolean,
  },
  components: {
    Button,
  },
  emits: ["toggle-add-task", "toggle-filter"],
  computed: {
    isHomePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
