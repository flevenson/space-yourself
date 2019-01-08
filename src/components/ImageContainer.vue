<template>
  <div class='main-container'>
    <div class='image-holder'>
      <img class='main-image' :src='mainSRC' alt='Nasa Image of the day'/>
    </div>
    <div class='button-holder'>
      <ul>
        <li v-for="image in images" v-bind:key='image.id' v-bind:id='image.id'><button v-on:click='setImage(image.src)'>View</button></li>
      </ul>
    </div>
  </div>
</template>

<script>

import image from '../assets/jupiter.jpg'
import image2 from '../assets/space_1.jpg'
import image3 from '../assets/space_2.jpeg'
import image4 from '../assets/space_cat.jpeg'


export default {
  name: 'ImageContainer',
  mainImage: this.image || image,
  data () {
    return {
      image: null,
      mainSRC: image,
      images: [
        {
          src: image,
          index: 0
        },
        {
          src: image2,
          index: 1,
        }, 
        {
          src: image3,
          index: 2
        },
        {
          src: image4,
          index:3
        }
        ]
    }
  },
  methods: {
    loadImage: function() {
      return '../assets/jupiter.jpg'
    },
    setImage: function(tag) {
      this.mainSRC = tag
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    height: 75vh;
  }
  .main-image {
    width: 500px;
  }
  
  .image-holder{
    width: 100vw;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
