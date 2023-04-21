<script setup >
import {ref} from 'vue';
import axios from 'axios';


let messages = ref(null);
let errorMessages = ref(false);
let successMessage = ref(false);

let firstName = ref(null);
let lastName = ref(null);
let email = ref(null);
let message = ref(null);


async function handleSubmit(){
    successMessage.value = false;
    errorMessages.value = false;

    axios.post("https://formspree.io/f/xbjeqypo", {
        "firstName": firstName.value,
        "lastName": lastName.value,
        "email": email.value,
        "message": message.value
    }).then(()=>{
        successMessage.value = true;
        messages.value.focus();
        setTimeout(()=>{
            successMessage.value = false;
        }, 4000)
    }).catch((err)=>{
        console.log(err.response.data, "start")
        errorMessages.value = true;
        messages.value.focus();
        setTimeout(()=>{
            errorMessages.value = false;
        }, 4000)
        // let errors = err.response.data.errors;
        //
        // if( errors.length >= 1 ){
        //     for (const error of errors) {
        //         errorMessages.value.push(error.message);
        //     }
        // }else{
        //     errorMessages.value.push("something went wrong");
        // }
        //
        // console.log(errorMessages.value)
    })
}


</script>

<template>
    <section class="section contact" id="contact">
        <h2 class="contact__header">Send us a message</h2>
    
        <div class="messages" ref="messages" v-if="successMessage || errorMessages">
            <div class="messages__success" v-if="successMessage">
                <p class="messages__success--message"  >Your Message Has Been Sent Successfully</p>
            </div>
            <div class="messages__error" v-if="errorMessages">
                <p class="messages__error--message">Something Went Wrong Please Try Again</p>
            </div>
        </div>

        <form @submit.prevent="handleSubmit" class="contact__form" >
            <fieldset class="contact__form--outerBox">
                <fieldset class="contact__form--innerBox">
                    <input v-model="firstName" id="" class="input input--outline input--gold contact__form--firstName" type="text" name="" placeholder="First Name" required autocomplete="firstName">
                    <input v-model="lastName" id="" class="input input--outline input--gold contact__form--lastName" type="text" name="" placeholder="Last Name" autocomplete="lastName" required>
                </fieldset>
                <input id="" class="input input--outline input--gold contact__form--email" type="email" name="" placeholder="Email" autocomplete="email" required>
                <textarea v-model="message" id="" class="input input--outline input--gold input--message contact__form--message" type="text" name="" placeholder="Please tell us more about your current needs" autocomplete="message" required></textarea>
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
    padding-bottom: 10vh;

    .messages{
        
        & > div {
            padding: 1em 4vw 1em 4vw;
            width: 100%;
            color: black;
            border-radius: 0.2em;
        }

        &__success{
            background-color: limegreen;
        }

        &__error{
            background-color: #ff0033;
        }
    }

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
