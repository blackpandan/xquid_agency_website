<script setup>
// code...
// import ScrollButton from '../ScrollButton.vue';
</script>

<template>
    <section class="section whatWeDo" id="whatWeDo">

        <h2 class="whatWeDo__header">WHAT WE DO</h2>

        <div class="whatWeDo__content">
            <div class="website">
                <p class="website__header whatWeDo--headers">
                    <img src="../../assets/icons/website.svg" alt="" class="website__header--icon whatWeDo--icons">
                    <span class="website__header--text">WEBSITE DEVELOPMENT</span>
                </p>
                <p class="website__text whatWeDo--texts">
                    We create custom websites using technologies and coding standards, aligned with our clients' brand and business goals.
                </p>
            </div>
            <div class="whatWeDo__server">
                <p class="server__header whatWeDo--headers">
                    <img src="../../assets/icons/server.svg" alt="" class="server__header--icon whatWeDo--icons">
                    <span class="server__header--text">SERVER MANAGEMENT</span>
                </p>
                <p class="server__text whatWeDo--texts">
            we also provide ongoing maintenance and support services to ensure our clients' websites stay up-to-date and secure.
                </p>
            </div>
        </div>
        <!-- <ScrollButton scrollTarget="contact" /> -->
    </section>
</template>

<style lang="scss" scoped>
/* code... */
.whatWeDo{
    flex-flow: column nowrap;
    align-items: center;
    height: fit-content;
    min-height: 100vh;
    gap: 14vh 0;
    padding-bottom: 10vh;


    &__header{
        font-size: calc(1em + 10vmin);
        font-family: vars.$font-family;
        color: vars.$offnet-color;
        padding-top: 1rem;
    }

    &__content{
        display: flex;
        flex-flow: row wrap;
        gap: 5em 15vw;
        align-items: center;
         
        & > div {
            flex: 1 1 200px;
        }
    }

    .website{
        &__header{
        }
    }

    &--headers{
        display: flex;
        flex-flow: column nowrap;
        padding: 0 0 3vh 0;
        font-size: calc(1em + 2.5vmin);
        font-family: vars.$font-family;
        color: vars.$offnet-color;
        gap: 1.5vh 0;
        align-items: center;
        text-align: center;
    }

    &--icons{
        width: calc(1em + 3vmin);
        height: calc(1em + 3vmin);
    }

    &--texts{
        font-size: calc(0.8em + 0.8vmin);
        font-family: vars.$font-Merriweather;
        align-items: center;
        text-align: center;
    }
}

/* @media only screen and (max-width: 549px){ */
/*     .whatWeDo{ */
/*         &__content{ */
/*  */
/*         } */
/*  */
/*         &--headers{ */
/*             align-items: center; */
/*             text-align: center; */
/*         } */
/*  */
/*         &--texts{ */
/*             align-items: center; */
/*             text-align: center; */
/*         } */
/*     } */
/* } */

</style>
