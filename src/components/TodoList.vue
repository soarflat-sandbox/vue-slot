<template>
  <ul>
    <li v-for="todo in todos" v-bind:key="todo.id">
      <slot name="todo" v-bind:todo="todo">
        {{ todo.text }}
      </slot>
    </li>
  </ul>
</template>

<script>
export default {
  name: "TodoList",
  props: {
    todos: Array
  }
};
</script>
