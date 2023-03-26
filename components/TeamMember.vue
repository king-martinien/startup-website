<template>
  <div class="member">
    <div class="member-avatar">
      <img
        :src="`images/avatars/${avatar}`"
        alt="member avatar"
        loading="lazy"
      />
    </div>
    <h4 class="member-name">{{ name }}</h4>
    <div class="member-profession text-upper">{{ profession }}</div>
  </div>
</template>

<script setup>
defineProps({
  avatar: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true,
  },

  profession: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.member {
  border-radius: 5px;
  box-shadow: 3px 4px 12px 1px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: column;
  gap: 17px;
  padding: 18px 24px;
  max-width: 270px;

  &-avatar {
    width: 175px;
    height: 176px;
    border-radius: 50%;
    border: 1px solid var(--clr-gray);
    overflow: hidden;
    align-self: center;
    display: flex;
    justify-content: center;
    align-items: flex-end;
  }

  &-name {
    font-size: 1.5rem;
    color: var(--clr-dark);
  }

  &-profession {
    color: var(--clr-dark-75);
  }

  @media screen and (min-width: 375px) {
    width: 279px;
    margin: 0 auto;
  }

  @media screen and (min-width: 768px) {
    flex: 1;
    margin: 0;
  }
}
</style>
