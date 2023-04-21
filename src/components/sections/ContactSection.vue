<script setup >
</script>

<template>
    <section class="section contact" id="contact">
        <h2 class="contact__header">Send us a message</h2>
        <form action="" class="contact__form">
            <fieldset class="contact__form--outerBox">
                <fieldset class="contact__form--innerBox">
                    <input id="" class="input input--outline input--gold contact__form--firstName" type="text" name="" placeholder="First Name">
                    <input id="" class="input input--outline input--gold contact__form--lastName" type="text" name="" placeholder="Last Name">
                </fieldset>
                <input id="" class="input input--outline input--gold contact__form--email" type="email" name="" placeholder="Email">
                <textarea id="" class="input input--outline input--gold input--message contact__form--message" type="text" name="" placeholder="Please tell us more about your current needs"></textarea>
            </fieldset>
            <input class="button button--gold contact__form--submit" type="submit" value="Send">
        </form>
    </section>
</template>

<style lang="scss" scoped>
.contact{
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    gap: 10vmin 0;
    padding-left: 8vmin;
    padding-right: 8vmin;

    &__header{
        font-family: vars.$font-family;
        /* color: vars.$offnet-color; */
        color: vars.$secondary-color;
        font-size: calc(1em + 5vmin);
    }

    &__form{
        display: flex;
        flex-flow: column nowrap;
        gap: 2em 0;
        width: fit-content;

        &--firstName{

            flex: 1 1 190px;
        }

        &--lastName{
            flex: 1 1 190px;
        }
        
        &--outerBox{
            display: flex;
            flex-flow: column nowrap;
            gap: 1em 0;
            border: none;
            
        }
        &--innerBox{
            display: flex;
            flex-flow: row wrap;
            border: none;
            gap: 1em 2vmin;
        }
    }
}
</style>
