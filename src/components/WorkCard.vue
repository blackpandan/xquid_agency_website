<script setup>
// code...

  let props = defineProps({
    data: Object
  })

  
</script>

<template>
  <div class="workCard">
    <div class="workCard__imgBox"><img class="workCard__imgBox--img" :src="data.imgUrl" alt=""></div>
    <div class="workCard__info">
      <div class="workCard__info--textBox">
        <h3 class="workCard__info--header">{{ data.header }}</h3>
        <p class="workCard__info--text">{{ data.info }}</p>
      </div>
      <button v-if="data.url" class="button button--black workCard__info--button">view work</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
/* code... */

.workCard{
  display: flex;
  flex-flow: row wrap;
  gap: 0.5em 1vw;
  background-color: transparentize(vars.$primary-color, 0.96);
  border: 2px solid transparentize(vars.$primary-color, 0.96);
  border-radius: 0.2em;
  max-width: 65vw;

  & > div{
    flex: 1 1 250px;
  }

  &__imgBox{
    /* width: 26vw; */
    height: 43vmin;
    padding: 0vmin;

    &--img{
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__info{
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-between;
    padding: 1em 8vmin 1em 2vmin;
    width: 30vw;
    gap: 2em 0;

    &--textBox{
      display: flex;
      flex-direction: column;
      gap: 0.5em 0;
    }

    &--header{
      font-size: calc(1em + 3vmin);
      font-family: vars.$font-family;
    }
    // &--text{
    //
    // }
    &--button{
      width: fit-content;
    }
  }
}

@media only screen and (max-width: 450px) {
  .workCard{
    max-width: 80vw;
  }
}
</style>
