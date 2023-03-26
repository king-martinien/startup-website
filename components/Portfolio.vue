<template>
  <div class="portfolio">
    <img :src="portfolio.images" :alt="portfolio.title" />
  </div>
</template>

<script setup>
defineProps({
  portfolio: {
    type: Object,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.portfolio {
  border: 2px solid var(--clr-dark);
  border-radius: 5px;
  overflow: hidden;
  display: flex;
  min-height: 215px;

  &:hover {
    img {
      transform: scale(1.1);
    }
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: inherit;
    transition: all 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
  }

  @media screen and (min-width: 768px) {
    img {
      min-height: 340px;
    }
  }
}
</style>
