<template>
  <SectionHero />

  <section class="partners">
    <div class="partners-container container">
      <Heading
        sup-title="partners"
        title="Our Partners"
        description="Lorem ipsum, dolor sit amet consectetur
      Suscipit nemo hic quos, ab,"
      />
      <div class="partners-list">
        <div class="img">
          <img
            src="/icons/partners/google.svg"
            alt="google logo"
            loading="lazy"
          />
        </div>
        <div class="img">
          <img
            src="/icons/partners/microsoft.svg"
            alt="microsoft logo"
            loading="lazy"
          />
        </div>
        <div class="img">
          <img
            src="/icons/partners/airbnb.svg"
            alt="airbnb logo"
            loading="lazy"
          />
        </div>
        <div class="img">
          <img
            src="/icons/partners/facebook.svg"
            alt="facebook logo"
            loading="lazy"
          />
        </div>
        <div class="img">
          <img
            src="/icons/partners/spotify.svg"
            alt="spotify logo"
            loading="lazy"
          />
        </div>
      </div>

      <button class="btn btn-dark">Learn more</button>
    </div>
  </section>

  <Section
    section-img="section-img.png"
    title="Lorem ipsum dolor sit amet consectetur"
    text="Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit
          nemo hic quos, ab, dolor aperiam nobis cum est eos error ipsum,
          voluptate culpa nesciunt delectus iste?"
  />

  <Section
    section-img="section-img-2.png"
    title="Lorem ipsum dolor sit amet consectetur"
    text="Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit
          nemo hic quos, ab, dolor aperiam nobis cum est eos error ipsum,
          voluptate culpa nesciunt delectus iste?"
    is-reverse
  />

  <section class="team">
    <div class="team-container container">
      <Heading
        sup-title="team"
        title="Our Talents"
        description="Lorem ipsum, dolor sit amet consectetur
      Suscipit nemo hic quos, ab,"
      />
      <div class="members">
        <TeamMember
          v-for="member in members"
          :avatar="member.avatar"
          :name="member.name"
          :profession="member.profession"
        />
      </div>

      <button class="btn btn-dark">View Team</button>
    </div>
  </section>
</template>

<script setup>
const members = ref([
  {
    avatar: "avatar-1.png",
    name: "Peg Legge",
    profession: "CEO",
  },
  {
    avatar: "avatar-2.png",
    name: "Richard Guerra",
    profession: "CTO",
  },
  {
    avatar: "avatar-3.png",
    name: "Alexandra Stolz",
    profession: "Designer",
  },
  {
    avatar: "avatar-4.png",
    name: "Janet Bray",
    profession: "Developper",
  },
]);

useHead({
  title: "Startup Website | Home",
  meta: [
    {
      hid: "description",
      name: "description",
      content:
        "Startup Website is a website template for startups and agencies that want to showcase their work and services.",
    },
    {
      hid: "og:title",
      property: "og:title",
      content: "Startup Website | Home",
    },
    {
      hid: "og:description",
      property: "og:description",
      content:
        "Startup Website is a website template for startups and agencies that want to showcase their work and services.",
    },
    {
      hid: "og:image",
      property: "og:image",
      content: "https://startup-website.vercel.app/hero-img.png",
    },
    {
      hid: "og:url",
      property: "og:url",
      content: "https://startup-website.vercel.app/",
    },
    {
      hid: "twitter:title",
      name: "twitter:title",
      content: "Startup Website | Home",
    },
    {
      hid: "twitter:description",
      name: "twitter:description",
      content:
        "Startup Website is a website template for startups and agencies that want to showcase their work and services.",
    },
    {
      hid: "twitter:image",
      name: "twitter:image",
      content: "https://startup-website.vercel.app/hero-img.png",
    },
    {
      hid: "twitter:card",
      name: "twitter:card",
      content: "summary_large_image",
    },
    {
      hid: "twitter:site",
      name: "twitter:site",
      content: "@startup-website",
    },
    {
      hid: "twitter:creator",
      name: "twitter:creator",
      content: "@startup-website",
    },
    {
      hid: "twitter:url",
      name: "twitter:url",
      content: "https://startup-website.vercel.app/",
    },
  ],
});
</script>

<style lang="scss" scoped>
.team,
.partners {
  padding: 50px 0;

  &-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 45px;
  }
}
.team {
  .members {
    display: flex;
    flex-direction: column;
    gap: 40px;
  }
}

.partners {
  &-list {
    display: flex;
    flex-direction: column;
    gap: 30px;

    .img {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 140px;
    }
  }
}

@media screen and (min-width: 768px) {
  .team {
    .members {
      flex-direction: row;
      justify-content: center;
      flex-wrap: wrap;
    }
  }

  .partners {
    &-list {
      flex-direction: row;
      align-self: stretch;
      gap: 50px;

      .img {
        width: auto;
        flex: 1;

        img {
          width: 100%;
          filter: grayscale(100%);
          transform: scale(0.9);
          transform-origin: center;
          transition: 0.3s ease-in-out;
          user-select: none;
          -webkit-user-drag: none;

          &:hover {
            filter: grayscale(0);
            transform: scale(1);
          }
        }
      }
    }
  }
}
</style>
