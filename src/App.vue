<template>
  <div id="app">
    <div class="heading-holder">
      <span class="heading">SpaceYourself</span>
    </div>
    <ImageContainer/>
  </div>
</template>

<script>
import ImageContainer from './components/ImageContainer'

export default {
  name: 'App',
  components: {
    ImageContainer
  }
}
</script>

<style>
    .heading-holder {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
  }
</style>
