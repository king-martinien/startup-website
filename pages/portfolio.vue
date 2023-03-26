<template>
  <Heading
    sup-title="works"
    title="Portfolio"
    description="Lorem ipsum, dolor sit amet consectetur
    adipisicing elit."
  />

  <div class="portfolios">
    <div class="portfolios-container container">
      <Portfolio
        v-for="portfolio in portfolios"
        :key="portfolio.id"
        :portfolio="portfolio"
      />
    </div>
  </div>
</template>

<script setup>
useHead({
  title: "Startup Website | Portfolio",
  meta: [
    {
      name: "description",
      content: "Portfolio",
    },
  ],
});

const portfolios = ref([
  {
    id: 1,
    title: "Portfolio 1",
    images: "/images/portfolio/portfolio-1.png",
  },
  {
    id: 2,
    title: "Portfolio 2",
    images: "/images/portfolio/portfolio-2.png",
  },
  {
    id: 3,
    title: "Portfolio 3",
    images: "/images/portfolio/portfolio-3.png",
  },
  {
    id: 4,
    title: "Portfolio 4",
    images: "/images/portfolio/portfolio-4.png",
  },
  {
    id: 5,
    title: "Portfolio 5",
    images: "/images/portfolio/portfolio-5.png",
  },
  {
    id: 6,
    title: "Portfolio 6",
    images: "/images/portfolio/portfolio-6.png",
  },
  {
    id: 7,
    title: "Portfolio 7",
    images: "/images/portfolio/portfolio-7.png",
  },
  {
    id: 8,
    title: "Portfolio 8",
    images: "/images/portfolio/portfolio-8.png",
  },
]);
</script>

<style lang="scss" scoped>
.portfolios {
  padding: 2rem 0 5rem;
  &-container {
    display: grid;
    gap: 55px;

    @media screen and (min-width: 768px) {
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    }

    @media screen and (min-width: 1130px) {
      grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
    }
  }
}
</style>
