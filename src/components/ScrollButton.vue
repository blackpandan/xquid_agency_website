<script setup >
const props = defineProps({
  scrollTarget: String
})

</script>

<template>
  <a :href="'#' + scrollTarget" class="scrollButton">
    <h4 class="scrollButton__text">scroll</h4>
    <button class="scrollButton__button">
    <i class="material-symbols-rounded scrollButton__button--icon">arrow_downward</i>
    </button>
  </a>
</template>

<style lang="scss" scoped>
.scrollButton{
  position: absolute;
  bottom: calc(1em + 1vmin);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.4em 0;

  &__text{
    font-family: Arial, Helvetica, sans-serif;
    font-weight: 400;
    font-size: 1em;
    color: vars.$offnet-color;
  }

  &__button{
    background-color: vars.$offnet-color;
    border: 1px solid vars.$offnet-color;
    border-radius: 50%;
    width: calc(1em + 2vmin);
    height: calc(1em + 2vmin);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;

    &--icon{
      font-size: calc(1em + 1vmin);
    }

    &:hover{
      background-color: transparent;
      color: vars.$secondary-color;
    }
  
  }

}
</style>
