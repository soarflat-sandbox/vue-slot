<template>
  <a :href="url" class="nav-link">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: "NavigationLink",
  props: {
    url: String
  }
};
</script>
