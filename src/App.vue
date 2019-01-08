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
    ImageContainer,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Berkshire+Swash');

  .heading-holder {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
  }

  .heading {
    font-size: 4rem;
    margin: 0 10px;
    font-family: 'Berkshire Swash', cursive;
    color: white;
  }
  
  #app {
    background-color: gray;
    display: flex;
    align-items: center;
    flex-direction: column;
    min-height: 100vh;
  }
</style>
