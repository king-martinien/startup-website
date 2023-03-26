<template>
  <section class="section" :class="{ reverse: isReverse, hero: isHero }">
    <div class="section-container container">
      <div class="section-img">
        <img
          :src="`/images/${sectionImg}`"
          alt="section image"
          loading="lazy"
        />
      </div>
      <div class="section-description">
        <h3>{{ title }}</h3>
        <p>{{ text }}</p>
        <button class="btn" :class="btnClass">
          {{ isHero ? "Explore" : "Learn more" }}
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  sectionImg: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  text: {
    type: String,
    required: true,
  },
  isReverse: {
    type: Boolean,
    default: false,
  },
  isHero: {
    type: Boolean,
    default: false,
  },
});

const btnClass = computed(() => {
  return props.isHero ? "btn-white" : "btn-dark";
});
</script>

<style lang="scss" scoped>
.section {
  &-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 30px;
  }

  margin-bottom: 40px;
  &:not(&.reverse) {
    margin: 60px 0;
  }

  &-description {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    gap: 20px;

    h3 {
      font-size: 24px;
    }
    p {
      color: var(--clr-dark-50);
    }
  }

  @media screen and (min-width: 375px) {
    &-description {
      h3 {
        font-size: 32px;
        line-height: 34px;
      }
    }
  }

  @media screen and (min-width: 768px) {
    &-container {
      flex-direction: row;
      justify-content: space-between;
      gap: 50px;
    }
    &.reverse {
      .container {
        flex-direction: row-reverse;
      }
    }

    &-img {
      max-width: 600px;
    }

    &-description {
      align-items: flex-start;
      text-align: left;
      max-width: 400px;
    }
  }
}
</style>
