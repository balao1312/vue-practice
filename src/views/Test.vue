<template>
  <div class="ctn">
    <div
      class="blk"
      @mouseover="mouseEvent($event, 5)"
      @mouseleave="mouseEvent($event, 8)"
      @dblclick="mouseEvent"
    >
      Test Section
    </div>
    <div class="blk" @mousemove="mouseMovement">
      position - {{ x }} - {{ y }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Test",
  props: {},
  inheritAttrs: false, //disable 'non-props' waring
  data() {
    return {
      x: 0,
      y: 0,
    };
  },
  methods: {
    mouseEvent(e, data) {
      console.log(e, e.type);
      if (data) {
        console.log(data);
      }
    },
    mouseMovement(e) {
      (this.x = e.offsetX), (this.y = e.offsetY);
    },
  },
};
</script>

<style scoped>
.blk {
  background-color: hsl(40, 100%, 90%);
  border: 3px solid hsl(200, 100%, 50%);
  border-radius: 10px;
  margin-bottom: 10px;
  padding: 10px;
  width: 200px;
  height: 50px;
}
.ctn {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}
</style>
