<script setup>
import { ref, onMounted } from 'vue';
import HamBurgerIcon from './HamBurgerIcon.vue';

const navBar = ref(null);
const root = document.documentElement;

function setNavBar(){
  root.style.setProperty('--nav-height', `${navBar.value.getBoundingClientRect().height + 10}px`)
}


onMounted(()=>{
  setNavBar();
  window.addEventListener('resize', ()=>{
    setNavBar();
  })
});

</script>

<template>
  <header class="navBar" ref="navBar" >
    
    <p class="navBar__logo"><img class="navBar__logo--img" src="../assets/img/logo-gold.png" /><span>XQUID</span></p>

    <nav class="nav nav--desktop" role="navigation">
      <a href="#landing" class="nav__link nav__link--home">home
      </a>
      <a href="#works" class="nav__link nav__link--projects">projects
      </a>
      <a href="#whatWeDo" class="nav__link nav__link--about">about
      </a>
      <a href="#contact" class="button button--gold nav__link nav__link--talk">let's talk
      </a>
    </nav> 
    
    <HamBurgerIcon />

  </header>
</template>

<style lang="scss">
.navBar{
  z-index: 9999;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-flow: row nowrap;
  padding: 1.5em 6vw 1.5em 6vw;
  font-size: calc(1em + 0.2vmin);
  /* background-color: vars.$primary-color; */
  /* background-color: vars.$secondary-color; */
  /* color: vars.$primary-color; */
  background-color: var(--nav-background-color);
  color: var(--nav-color);
  height: fit-content;
  transition: color cubic-bezier(0.19, 1, 0.22, 1) 0.3s, background-color cubic-bezier(0.19, 1, 0.22, 1) 0.3s;

  &__logo{
    font-family: vars.$font-family;
    font-size: 1.6em;
    text-align: end;
    display: flex;
    flex-flow: row nowrap;
    align-items: flex-end;
    gap: 0 0.2em;

    &--img{
      max-height: 1.5em;
    }


  }

  .nav{
    display: flex;
    align-items: center;
    gap: 0 2vw;

    &__link{


      &:hover{
        text-decoration: underline vars.$offnet-color;
      }

      &--talk{
        font-size: 1em;
      }
      
    }
  }
}

@media only screen and (max-width: 730px){
  .navBar{
    .nav{
      &--desktop{
        display: none;
      }
    }
  }
}
</style>
