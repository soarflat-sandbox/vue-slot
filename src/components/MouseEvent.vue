<template>
  <div @mousemove="mousemove">
    <slot :x="x" :y="y"></slot>
  </div>
</template>

<script>
export default {
  name: "MouseEvent",
  data() {
    return {
      x: 0,
      y: 0
    };
  },
  methods: {
    mousemove(e) {
      this.x = e.clientX;
      this.y = e.clientY;
    }
  }
};
</script>
