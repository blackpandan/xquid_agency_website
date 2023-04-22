<script setup lang="ts">
// code...
</script>

<template>
  <div class="hambu">

    <input class="hambu__toggle" id="" type="checkbox" name="" aria-label="hamburge icon toggle" />

    <div class="hamburger">
      <span class="hamburger__line"></span>
      <span class="hamburger__line"></span>
      <span class="hamburger__line"></span>
    </div>
  

    <div class="hambu__menu">
      <a href="#landing" class="hambu__menu--item">home
      </a>
      <a href="#works" class="hambu__menu--item">projects
      </a>
      <a href="#whatWeDo" class="hambu__menu--item">about
      </a>
      <a href="#contact" class="button button--gold nav__link nav__link--talk">let's talk
      </a>
    </div> 

  </div>
</template>

<style lang="scss" scoped>
/* code... */
.hambu{
  display: block;
  position: absolute;
  top: 50%;
  right: 6vw;
  width: calc(0.6em + 3.8vmin);
  height: calc(0.6em + 2.5vmin);
  transform: translateY(-50%);

  &__toggle{
    display: block;
    transform: translate(-50%, -50%);
    position: absolute;
    cursor: pointer;
    top: 50%;
    left: 50%;
    z-index: 3;
    width: 120%;
    height: 130%;
    -webkit-touch-callout: none; 
    opacity: 0;

  }
  &__menu{
    display: none;
    flex-direction: column;
    position: absolute;
    align-items: center;
    top:0;
    right: 0;
    margin: -2em -6vw 0 0;
    padding: 8em 6vw 0 6vw;
    color: vars.$primary-color;
    /* right: 1px; */
    /* left: 1px; */
    background: vars.$secondary-color;
    height: 100vh;
    width: 100vw;
    font-size: calc(0.6em + 1.8vmin);
    gap: 1em 0;
    z-index: 1;
    -webkit-font-smoothing: antialiased;

    &--item{
      padding: 0.1em 0 0.1em 0;
      border-bottom: 2px solid vars.$secondary-color;

      &:hover{
        border-bottom-color: vars.$offnet-color;
      }
    }
  }

  & input:checked ~ div>span{
    opacity: 1;
    transform: rotate(-45deg) translate(0, calc(-0.15em + -0.2vmin));
    background-color: vars.$primary-color;
  }

  & input:checked ~ div>span:nth-last-child(3){
    transform: rotate(45deg) translate(0, calc((-0.15em + -0.2vmin) / 2));
  }

  & input:checked ~ div>span:nth-last-child(2){
    opacity: 0;
    transform: rotate(0deg) scale(0.2, 0.2);
  }

  & input:checked ~ .hambu__menu {
    display: flex;
  }

}

.hamburger{
  /* width: calc(0.6em + 3.8vmin); */
  /* height: calc(0.6em + 2.5vmin); */
  width: 100%;
  height: 100%;
  position: absolute;
  top: 50%;
  /* top: 2.85em; */
  /* right: 6vw; */
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  cursor: pointer;
  justify-content: space-between;
  display: none;
  -webkit-user-select: none;
  user-select: none;
  z-index: 2;

  &__line{
    display: block;
    width: 100%;
    height: calc(0.15em + 0.2vmin);
    /* background-color: vars.$secondary-color; */
    background-color: vars.$offnet-color;
    /* background-color: vars.$primary-color; */
    border-radius: 10px;
    z-index: 1;
    transform-origin: calc(0.15em + 0.2vmin) 0px;
    transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0), background-color 0.5s cubic-bezier(0.77,0.2,0.05,1.0), opacity 0.55s ease;

    &:first-child{
      transform-origin: 0% 0%;
    }

    &:nth-last-child(2){
      transform-origin: 0% 100%;
    }
  }

}

@media only screen and (max-width: 730px){
  .hamburger{
    display: flex;
  }
}
</style>
