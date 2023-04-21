<script setup>
// code...
    // import ScrollButton from '../ScrollButton.vue';
    import SocialLinks from '../SocialLinks.vue';
</script>

<template>
    <section class="section aboutUs" id="aboutUs">
        <div class="aboutUs__box">
            <h1 class="aboutUs__header">ABOUT US</h1>
            <p class="aboutUs__text">
                We're a web development agency passionate about building high-quality websites tailored to our clients' needs, using the most efficient technologies and best practices.
            </p>
        </div>
        <!-- <ScrollButton scrollTarget="works" /> -->
        <SocialLinks />
    </section>
</template>

<style lang="scss" scoped>
/* code... */

.aboutUs{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-flow: column nowrap;

    &__box{
        text-align: center;
        padding: 3em 15vw 2em 15vw;
        display: flex;
        gap: 2em 0;
        flex-flow: column nowrap;
        padding-bottom: calc(var(--nav-height) * 2);
    }

    &__header{
        color: vars.$offnet-color;
        font-size: calc(1em + 10vmin);
        font-family: vars.$font-family;
    }

    &__text{
        font-size: calc(0.8em + 1vmin);
        font-family: vars.$font-Merriweather;
    }
}
</style>
