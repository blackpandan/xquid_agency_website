<script setup>
const props = defineProps(['loader'])
</script>

<template scoped>
  <div class="loader" v-if="props.loader">
    <div class="loader-element"></div>
  </div>
</template>

<style lang="scss" scoped>
.loader {
  font-size: calc( 3em + 3vmin);
  padding: 1em;
}

.loader-element {
  border-right: 0.1em solid currentcolor;
  border-radius: 100%;
  -webkit-animation: loader-element 800ms linear infinite;
  animation: loader-element 800ms linear infinite;
  
  &:before, &:after {
    content: "";
    width: 0.8em;
    height: 0.8em;
    display: block;
    position: absolute;
    top: calc(50% - .4em);
    left: calc(50% - .4em);
    border-left: 0.08em solid currentcolor;
    border-radius: 100%;
    animation: loader-37 400ms linear infinite reverse;

  }
  &:after {
    width: 0.6em;
    height: 0.6em;
    top: calc(50% - .3em);
    left: calc(50% - .3em);
    border: 0;
    border-right: 0.05em solid currentcolor;
    -webkit-animation: none;
    animation: none;
    
  }
}

@-webkit-keyframes loader-element {
  from {
    transform: rotate(360deg);
  }
  to {
    transform: rotate(0deg);
  }

}

@keyframes loader-element {
  from {
    transform: rotate(360deg);
  }
  to {
    transform: rotate(0deg);
  }
}
</style>
