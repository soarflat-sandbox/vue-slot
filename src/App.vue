<template>
  <div id="app">
    <navigation-link url="/profile">
      <font-awesome-icon></font-awesome-icon>
      Your Profile
      {{ name }}
    </navigation-link>

    <submit-button></submit-button>
    <submit-button>Sutton submit!!</submit-button>

    <base-layout>
      <template v-slot:header>
        <h1>Here might be a page title</h1>
      </template>

      <p>A paragraph for the main content.</p>
      <p>And another one.</p>

      <!-- []で動的なスロット名を指定できる -->
      <template v-slot:[dynamicSlotName]>
        <p>Here's some contact info</p>
      </template>
    </base-layout>

    <current-user></current-user>
    <current-user>
      <template v-slot:default="slotProps">
        {{ slotProps.user.firstName }}
      </template>
    </current-user>

    <current-user v-slot:default="slotProps">
      {{ slotProps.user.firstName }}
    </current-user>

    <current-user v-slot="slotProps">
      {{ slotProps.user.firstName }}
    </current-user>

    <current-user v-slot="{ user }">
      {{ user.firstName }}
    </current-user>

    <base-layout>
      <!-- v-slotは#で省略可能 -->
      <template #header>
        <h1>Here might be a page title</h1>
      </template>

      <p>A paragraph for the main content.</p>
      <p>And another one.</p>

      <template #footer>
        <p>Here's some contact info</p>
      </template>
    </base-layout>

    <todo-list v-bind:todos="todos">
      <template v-slot:todo="{ todo }">
        <span v-if="todo.isComplete">✓</span>
        {{ todo.text }}
      </template>
    </todo-list>
  </div>
</template>

<script>
import NavigationLink from "./components/NavigationLink.vue";
import FontAwesomeIcon from "./components/FontAwesomeIcon.vue";
import SubmitButton from "./components/SubmitButton.vue";
import BaseLayout from "./components/BaseLayout.vue";
import CurrentUser from "./components/CurrentUser.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "app",
  components: {
    NavigationLink,
    FontAwesomeIcon,
    SubmitButton,
    BaseLayout,
    CurrentUser,
    TodoList
  },
  data() {
    return {
      name: "soarflat",
      dynamicSlotName: "footer",
      todos: [
        {
          id: 1,
          isComplete: false,
          text: "clean"
        },
        {
          id: 2,
          isComplete: true,
          text: "study"
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
