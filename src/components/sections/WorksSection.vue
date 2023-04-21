<script setup>
import {onMounted, ref} from 'vue';
import WorkCard from '../WorkCard.vue';

const works = ref(null);
  let datas =  [
    {
      imgUrl: "/worksImage/luxe.png",
      header: "LUXE CROWN AFRICA",
      info: "this is a sample site that was made to aid those that intended to be aided",
      url: "y",
    },
    {
      imgUrl: "/worksImage/skarstrokes.png",
      header: "SKARSTROKES STUDIO",
      info: "this is a sample site that was made to aid those that intended to be aided",
      url: "",
    },
    {
      imgUrl: "/worksImage/xquid.png",
      header: "XQUID WEB AGENCY",
      info: "this is a sample site that was made to aid those that intended to be aided",
      url: "",
    }
]


onMounted(()=>{
    window.addEventListener('scroll', ()=>{

  const root = document.documentElement;
        if(works.value.getBoundingClientRect().top < 95 && works.value.getBoundingClientRect().bottom > 95) {
            root.style.setProperty('--nav-background-color', '#F5F5FA')
            root.style.setProperty('--nav-color', '#0F0C0C')
        }else{
            root.style.setProperty('--nav-background-color', '#0F0C0C')
            root.style.setProperty('--nav-color', '#F5F5FA')
        }

    })
})
</script>

<template>
    <section class="section works" id="works" ref="works">
        <h2 class="works__header" >SELECTED WORKS</h2>
        <div class="works__collection">
            <WorkCard v-for="(data, index) in datas" :key="index" :data="data"  />
        </div>
    </section>
</template>

<style lang="scss" scoped>
.works{
    display: flex;
    align-items: center;
    flex-flow: column nowrap;
    background-color: vars.$secondary-color;
    color: vars.$primary-color;
    gap: 17vmin 0;
    padding-bottom: 20vh;

    &__header{
        padding: 0.5em 0 0 0;
        font-size: calc(1em + 9vmin);
        font-family: vars.$font-family;
        color: lighten(vars.$primary-color, 5);
        
    }

    &__collection{
        display: flex;
        flex-flow: column nowrap;
        gap: 20vmin 0;
    }

}
</style>
