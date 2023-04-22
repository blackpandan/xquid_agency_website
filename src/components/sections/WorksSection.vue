<script setup>
import {onMounted, ref} from 'vue';
import WorkCard from '../WorkCard.vue';

const works = ref(null);
  let datas =  [
    {
      imgUrl: "/worksImage/luxe",
      header: "LUXE CROWN AFRICA",
      info: "A website created for Luxe a pageantry company that allows contestants to easily create and manage their accounts and profiles. The website featured a secure payment processing system through Paystack for user voting and an admin panel to track contestant information, votes, and payments.",
      url: "",
    },
    {
      imgUrl: "/worksImage/skarstrokes",
      header: "SKARSTROKES STUDIO",
      info: "A website made for Skarstrokes a digital art studio that showcases their artworks and includes a custom CMS for easy management of their pictures. The website's user-friendly interface highlights the studio's works, while a contact form allows users to reach out to the studio",
      url: "",
    },
    {
      imgUrl: "/worksImage/ujgist",
      header: "UJGIST CONFESSION",
      info: "A website made for Ujgist a WhatsApp TV that allows anonymous confessions through a custom form. The website also features an admin panel, accessible through login credentials, for the admin to read and delete confessions",
      url: ""
    },
    {
      imgUrl: "/worksImage/xquid",
      header: "XQUID WEB AGENCY",
      info: "Our website which is a sample itself, of our works.",
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
