<template>
  <span>
    <slot :user="user">{{ user.lastName }}</slot>
  </span>
</template>

<script>
export default {
  name: "CurrentUser",
  data() {
    return {
      user: {
        firstName: "flat",
        lastName: "soar"
      }
    };
  }
};
</script>
