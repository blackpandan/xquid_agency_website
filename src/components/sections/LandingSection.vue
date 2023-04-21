<script setup>
import SocialLinks from '../SocialLinks.vue'
import ScrollButton from '../ScrollButton.vue'

</script>

<template>
    <section class="section landing" id="landing">

      <div class="landing__box">
        <h2 class="landing__create">WE CREATE </h2>
        <h1 class="landing__design">DESIGN THAT </h1>
          <h1 class="landing__design">TELLS YOUR STORY</h1>
      </div>
      <!-- <div class="backgroundText"> -->
      <!--   <p class="backgroundText__text">LESS IS MORE</p> -->
      <!--   <p class="backgroundText__text">LESS IS MORE</p> -->
      <!-- </div> -->
      <SocialLinks />
      <ScrollButton scrollTarget="aboutUs" />
    </section>
</template>

<style lang="scss" scoped>
.landing{
  position: relative;
    font-family: vars.$font-family;
    align-items: center;
    justify-content: center;
    flex-flow: column nowrap;
    z-index: 1;
    /* height: calc(100vh - var(--nav-height)) !important; */
    /* margin-top: var(--nav-height); */
    padding-top: 0 !important;

    overflow: hidden;
    &__box{
     // position: absolute;
      text-align: center;
      z-index: 1;
      padding: 0 0 0 0;
      margin-bottom: var(--nav-height);
    }

    &__create{
      font-size: calc(6vmin + 1em);
      line-height: 0.9em;
      color: transparent;
      -webkit-text-stroke: 0.8px opacify(vars.$offnet-color, 0.4);
      text-align: center;
      z-index: 1;
    }

    &__design{
      font-size: calc(18vmin + 1em);
      line-height: 0.9em;
      text-align: center;
    }

    .backgroundText{
      position: absolute;
      /* padding-top: var(--nav-height); */
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      white-space: nowrap;
      z-index: -1;
      line-height: calc((21vmin) * 2);
      max-height: 100%;
      overflow: hidden;

      &__text{
        font-family: vars.$font-family;
        font-size: calc(1em + 41vmin);
        letter-spacing: 1vmin;
        color: transparentize(darken(white, 65), 0.96)
      
      }
    }
  }
</style>
