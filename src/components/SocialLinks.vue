<script setup >
</script>

<template>
  <div class="socialLinks">
    <div class="socialLinks__icons">
      <a href="https://facebook.com/xquidtech/" target="_blank">
        <img src="../assets/icons/facebook.svg" alt="facebook logo" class="socialLinks__icons--icon">
      </a>
      <a href="https://linkedin.com/in/xquidtech/" target="_blank">
        <img src="../assets/icons/linkedin.svg" alt="linkedin logo" class="socialLinks__icons--icon">
      </a>
      <a href="https://www.instagram.com/xquidtech/" target="_blank">
        <img src="../assets/icons/instagram.svg" alt="instagram logo" class="socialLinks__icons--icon">
      </a>
      <a href="https://twitter.com/xquidtech/" target="_blank">
        <img src="../assets/icons/twitter.svg" alt="twitter logo" class="socialLinks__icons--icon">
      </a>
    </div>
    <div class="socialLinks__line"></div>
  </div>
</template>

<style lang="scss" scoped>
.socialLinks{
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  position: absolute;
  right: 6vw;
  bottom: 0;
  gap: 4vh 0;
  
  &__icons{
    display: flex;
    flex-flow: column nowrap;
    gap: 2vh 0;

    &--icon{
      height: 4vmin;
      width: 4vmin;
    }
  }

  &__line{
    height: 15vh;
    background-color: transparentize(vars.$secondary-color, 0.7);
    width: 1px;
  }
}
</style>
