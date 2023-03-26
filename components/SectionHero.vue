<template>
  <section class="hero">
    <div class="hero-container container">
      <div class="hero-img">
        <img src="images/hero-img.png" alt="hero image" loading="lazy" />
      </div>
      <div class="hero-text">
        <p class="sup-title text-upper">Welcome</p>
        <h1 class="title">Lorem ipsum dolor sit amet consectetur</h1>
        <p class="description">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit
          nemo hic quos, ab, dolor aperiam nobis cum est eos error ipsum,
          voluptate culpa nesciunt delectus iste?
        </p>
        <button class="btn btn-white">Explore</button>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style lang="scss" scoped>
.hero {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--clr-green);
  color: var(--clr-white);
  min-height: 570px;

  &-container {
    display: flex;
    flex-direction: column;
    gap: 30px;
  }

  &-text {
    display: flex;
    flex-direction: column;
    gap: 10px;
    .sup-title {
      letter-spacing: 5px;
      font-weight: bold;
    }

    .title {
      font-size: 26px;
      line-height: 1.1;
    }
    .description {
      color: var(--clr-white-75);
    }
  }

  @media screen and (min-width: 375px) {
    &-text {
      gap: 15px;
    }
  }

  @media screen and (min-width: 520px) {
    padding: 40px 0;

    &-container {
      align-items: center;
      justify-content: center;
    }
  }

  @media screen and (min-width: 768px) {
    min-height: auto;
    padding: 50px 0;

    &-container {
      flex-direction: row-reverse;
    }

    &-text,
    &-img {
      flex: 1;
      gap: 10px;
    }
  }

  @media screen and (min-width: 1080px) {
    min-height: calc(575px - 80px);
    padding: 0;

    &-container {
      flex-direction: row-reverse;
      justify-content: space-between;
    }

    &-text {
      max-width: 420px;
      margin: 0;
      gap: 15px;

      .title {
        font-size: 42px;
        line-height: 1.2;
      }
    }

    &-img {
      max-width: 645px;
    }
  }
}
</style>
