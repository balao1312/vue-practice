<template>
  <button @click="onClick()" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
    msg: String,
  },
  methods: {
    onClick() {
      console.log(this.msg);
      this.$emit('btn-click')
    },
  },
};
</script>
