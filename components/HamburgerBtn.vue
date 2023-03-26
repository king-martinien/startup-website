<template>
  <button class="hamburger" v-on:click="onToggleButton()">
    <span class="hamburger-icon" :class="{ active: isToggled }"></span>
  </button>
</template>

<script setup>
const emit = defineEmits(["toggled"]);
const isToggled = ref(false);

/**
 * Toggle the hamburger button.
 */
function onToggleButton() {
  isToggled.value = !isToggled.value;
  emit("toggled", isToggled.value);
}
</script>

<style lang="scss" scoped>
.hamburger {
  position: relative;
  width: 25px;
  height: 30px;
  outline: none;
  z-index: 1000;

  &-icon {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100%;
    height: 3px;
    background-color: var(--clr-white);
    transform: translate(-50%, -50%);
    border-radius: 4px;

    &::before,
    &::after {
      content: "";
      position: absolute;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: inherit;
      border-radius: 4px;
      transition: all 0.2s ease;
    }

    &::before {
      transform: translateY(-0.4rem);
    }

    &::after {
      transform: translateY(0.4rem);
    }

    &.active {
      visibility: hidden;

      &::before,
      &::after {
        transform: translateY(0);
        visibility: visible;
      }

      &::before {
        transform: rotate(135deg);
      }

      &::after {
        transform: rotate(-135deg);
      }
    }
  }

  @media screen and (min-width: 375px) {
    width: 28px;
    height: 35px;

    &-icon {
      &::before {
        transform: translateY(-0.45rem);
      }

      &::after {
        transform: translateY(0.45rem);
      }
    }
  }

  @media screen and (min-width: 768px) {
    display: none;
  }
}
</style>
