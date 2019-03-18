<template>
  <div>
    <div>Item with scope</div>
    <div>x: {{ x }}</div>
    <div>y: {{ y }}</div>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: {
    x: Number,
    y: Number
  }
};
</script>
