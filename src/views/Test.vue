<template>
  <div>
    <!-- use of mouseEvent -->
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
    <br />

    <!-- use of grid -->
    <div class="grid">
      <div class="grid-item">1</div>
      <div class="grid-item">2</div>
      <div class="grid-item">3</div>
      <div class="grid-item">4</div>
      <div class="grid-item">5</div>
      <div class="grid-item">6</div>
      <div class="grid-item">7</div>
      <div class="grid-item">8</div>
      <div class="grid-item">9</div>
      <div class="grid-item">10</div>
      <div class="grid-item">11</div>
      <div class="grid-item">12</div>
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
.grid {
  background-color: green;
  display: grid;
  padding: 10px;
  grid-column-gap: 10px;
  grid-row-gap: 10px;
  grid-template-columns: 200px 200px auto;
}
.grid-item {
  background-color: white;
  text-align: center;
  font-size: 20px;
  padding: 20px;
}
</style>
