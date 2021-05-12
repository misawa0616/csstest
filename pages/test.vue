<template>
  <div>
    <div style="display: flex">
      <div class="wrap">
        <div class="rect red inlineBlock"></div>
        <div class="rect green inlineBlock"></div>
        <div class="rect yellow inlineBlock"></div>
      </div>
      <div class="wrap">
        <div class="rect red inlineBlock"></div>
        <div class="rect green inlineBlock"></div>
        <div class="rect yellow inlineBlock"></div>
      </div>
      <div class="rect blue sideToggle" @click="clickToggle"></div>
    </div>
    <div class="main wrap">
      <div class="rectMain red inlineBlock"></div>
      <div class="rectNav green inlineBlock" v-if="isOpen"></div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isOpen: true,
    };
  },
  methods: {
    clickToggle() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style scoped>
.sideToggle {
  position: absolute;
  top: 0;
  right: 0;
}
.rect {
  width: 100px;
  height: 100px;
}
.rectMain {
  width: calc(100% - 350px);
  height: 100%;
}
@media screen and (max-width: 1000px) {
  .rectMain {
    width: calc(100%);
    height: 100%;
  }
}
.main {
  position: relative;
  width: calc(100%);
  height: 700px;
}
.rectNav {
  width: 350px;
  height: 100%;
}
@media screen and (max-width: 1000px) {
  .rectNav {
    z-index: 1;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}
.red {
  background-color: red;
}
.blue {
  background-color: blue;
}
.green {
  background-color: green;
}
.yellow {
  background-color: yellow;
}
.inlineBlock {
  margin: 0px;
}
.wrap {
  display: flex;
  flex-direction: row;
  font-size: 0;
  word-spacing: 0px;
}
</style>