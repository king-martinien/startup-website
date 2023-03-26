<template>
  <header class="header">
    <div class="header-container container">
      <NuxtLink to="/" class="logo">
        <img src="icons/start-logo.svg" alt="Start Logo" loading="lazy" />
      </NuxtLink>
      <nav class="nav" :class="{ active: isNavToggled }">
        <ul class="nav-menu">
          <li class="nav-item">
            <NuxtLink class="nav-link" to="/">Home</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink class="nav-link" to="/portfolio">Portfolio</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink class="nav-link" to="/services">Services</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink class="nav-link" to="/contact">Contact</NuxtLink>
          </li>
        </ul>
      </nav>
      <HamburgerBtn @toggled="onToggleNav" />
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const isNavToggled = ref(false);

function onToggleNav(isToggled) {
  isNavToggled.value = isToggled;
}
</script>

<style lang="scss" scoped>
.header {
  background-color: var(--clr-green);
  color: var(--clr-white);
  height: 75px;
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  z-index: 1000;

  &-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
  }

  .logo {
    width: 100px;
    display: flex;
  }

  .nav {
    position: absolute;
    left: 0;
    width: 100%;
    top: 75px;
    background-color: var(--clr-dark-50);
    backdrop-filter: blur(3px);
    padding: 3rem 0;
    transform: translateX(-100%);
    transition: 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);

    &.active {
      transform: translateX(0);
    }

    &-menu {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 2rem;
    }

    &-link {
      font-weight: bold;
    }
  }

  @media screen and (min-width: 375px) {
    .logo {
      width: 120px;
    }
  }

  @media screen and (min-width: 768px) {
    height: 80px;
    .logo {
      width: 130px;
    }

    .nav {
      position: static;
      width: auto;
      border: none;
      padding: 0;
      transform: none;
      background-color: transparent;
      backdrop-filter: none;

      &-menu {
        align-items: center;
        flex-direction: row;
        gap: 30px;
      }

      &-link {
        display: inline-block;
        font-weight: normal;
        transition: 0.2s cubic-bezier(0.075, 0.82, 0.165, 1);
        position: relative;

        &::after {
          content: "";
          position: absolute;
          left: 0;
          bottom: -4px;
          width: 100%;
          height: 2px;
          background-color: var(--clr-white);
          border-radius: 4px;
          transform: scale(0);
          transform-origin: center;
        }

        &:hover {
          transform: scale(1.1);
          transform-origin: center;

          &::after {
            transform: scale(1);
            transition: 0.4s cubic-bezier(0.075, 0.82, 0.165, 1);
          }
        }
      }
    }
  }
}
</style>
