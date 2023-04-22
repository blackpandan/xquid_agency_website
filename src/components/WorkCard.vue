<script setup>
// code...

  let props = defineProps({
    data: Object
  })

  
</script>

<template>
  <div class="workCard">
    <div class="workCard__imgBox">
      <picture>
        <source :srcset="data.imgUrl+'-600.webp 600w,' +data.imgUrl+'-800.webp 800w, ' +data.imgUrl+'.webp 1440w'"
          sizes="(max-width: 520px) 600px,
          (max-width: 644px) 800px,
          1440px
          "
          type="image/webp" />
        <img class="workCard__imgBox--img" 
          :srcset="data.imgUrl+'-600.jpg 600w,'+data.imgUrl+'-800.jpg 800w, ' +data.imgUrl+'.jpg 1440w'"

          sizes="(max-width: 520px) 600px,
          (max-width: 644px) 800px,
          1440px"
          :src="data.imgUrl+'.jpg'" 
           :alt="data.header" />
      </picture>
    </div>
    <div class="workCard__info">
      <div class="workCard__info--textBox">
        <h3 class="workCard__info--header">{{ data.header }}</h3>
        <p class="workCard__info--text">{{ data.info }}</p>
      </div>
      <a :href="data.url" v-if="data.url" class="button button--black workCard__info--button">view work</a>
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
    padding: 1em 4vmin 1em 2vmin;
    width: 30vw;
    gap: 2em 0;

    &--textBox{
      display: flex;
      flex-direction: column;
      gap: 1em 0;
    }

    &--header{
      font-size: calc(1em + 4vmin);
      font-family: vars.$font-family;
    }
    &--text{
      font-size: calc(0.6em + 1.3vmin);
      color: transparentize($color: vars.$primary-color, $amount: 0.1);
      line-height: calc(0.8em + 1.3vmin);
    }
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
