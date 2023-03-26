<template>
  <div class="heading">
    <p class="sup-title text-upper">{{ supTitle }}</p>
    <h3 class="title">{{ title }}</h3>
    <p class="description">{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  supTitle: {
    type: String,
    required: true,
  },

  title: {
    type: String,
    required: true,
  },

  description: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.heading {
  display: flex;
  flex-direction: column;
  gap: 16px;
  align-items: center;
  text-align: center;
  max-width: 400px;
  margin: 0 auto;
  padding: 30px 0;
}
.sup-title {
  letter-spacing: 5px;
  color: var(--clr-green);
  font-weight: bold;
}

.title {
  font-size: 2.5rem;
}

.description {
  line-height: 1.5;
}
</style>
