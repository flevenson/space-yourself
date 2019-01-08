<template>
  <div class='main-container'>
    <div class='image-holder'>
      <img class='main-image' :src='mainSRC' alt='Nasa Image of the day'/>
    </div>
    <SearchForm />
    <div >
      <h2 class='past-images-heading'> Past Images </h2>
      <ul class='button-holder'>
        <li v-for="image in images" v-bind:key='image.id' v-bind:id='image.id'><button v-on:click='setImage(image.src)' class='view-button'>{{image.id}}</button></li>
      </ul>
    </div>
  </div>
</template>

<script>

import image from '../assets/jupiter.jpg'
import mockImages from '../assets/images.js'
import SearchForm from './SearchForm'


export default {
  name: 'ImageContainer',
  data () {
    return {
      mainSRC: 'https://images-na.ssl-images-amazon.com/images/I/81zm9tKLsxL._SX450_.jpg',
      images: mockImages
    }
  },
  components: {
    SearchForm,
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

<style scoped>
  .main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    height: 75vh;
  }
  .main-image {
    height: 45vh;
    border: 3px solid white;
    border-radius: 30px;
  }

  .past-images-heading {
    font-size: 2.5rem;
    color: white;
    text-align: center;
    font-family: 'Berkshire Swash', cursive;
    text-decoration: underline;
  }

  li {
    list-style-type: none;
  }

  .view-button {
    width: 40px;
    height: 40px;
    font-size: 1.1rem;
    background-color: black;
    color: white;
    border: 4px solid white;
    border-radius: 50px;
    margin: 2.5px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .image-holder{
    width: 100vw;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
  }

  .button-holder {
    width: 400px;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
  }
</style>
