<template>
  <div class="container">
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <!-- name のない <slot> 要素は、暗黙的に「default」という名前を持つ -->
      <slot></slot>
    </main>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script>
export default {
  name: "BaseLayout"
};
</script>
