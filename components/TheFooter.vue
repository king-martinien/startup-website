<template>
  <footer class="footer">
    <div class="footer-container container">
      <ul class="socials">
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/facebook.svg"
              loading="lazy"
              alt="facebook icon"
            />
          </NuxtLink>
        </li>
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/instagram.svg"
              loading="lazy"
              alt="instagram icon"
            />
          </NuxtLink>
        </li>
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/twitter.svg"
              loading="lazy"
              alt="twitter icon"
            />
          </NuxtLink>
        </li>
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/pinterest.svg"
              loading="lazy"
              alt="pinterest icon"
            />
          </NuxtLink>
        </li>
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/tiktok.svg"
              loading="lazy"
              alt="tiktok icon"
            />
          </NuxtLink>
        </li>
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/whatsapp.svg"
              loading="lazy"
              alt="whatsapp icon"
            />
          </NuxtLink>
        </li>
        <li class="social-item">
          <NuxtLink to="/" target="_blank" class="social-link">
            <img
              src="icons/socials/youtube.svg"
              loading="lazy"
              alt="youtube icon"
            />
          </NuxtLink>
        </li>
      </ul>
      <p class="copyright">© Start, 2022. All rights reserved.</p>
    </div>
  </footer>
</template>

<script setup></script>

<style lang="scss" scoped>
.footer {
  background-color: var(--clr-green);
  color: var(--clr-white);
  padding: 30px 0;

  &-container {
    display: flex;
    align-items: center;
    flex-direction: column;
    gap: 20px;
    text-align: center;
  }

  .socials {
    display: flex;
    align-items: center;
    gap: 20px;

    .social-link {
      display: flex;
    }
  }

  @media screen and (min-width: 768px) {
    padding: 50px 0;

    &-container {
      flex-direction: row;
      justify-content: space-between;
    }
  }
}
</style>
