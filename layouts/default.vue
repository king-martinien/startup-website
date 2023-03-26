<template>
  <TheHeader />
  <main class="main">
    <slot />
  </main>
  <TheFooter />
</template>

<script setup>
</script>

<style lang="scss" scoped>
.main {
  padding-top: 75px;

  @media screen and (min-width: 768px) {
    padding-top: 80px;
  }
}
</style>
