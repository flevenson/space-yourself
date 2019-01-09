<template>
  <div class='main-container'>
    <div class='image-holder'>
      <img class='main-image' :src='mainSRC' alt='Nasa Image of the day'/>
    </div>
    <form class='search-form' v-on:submit.prevent='searchAPI(searchText)'>
      <input class='search-input' type='text'  v-model="searchText" placeholder='type a search' />
    </form>
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


export default {
  name: 'ImageContainer',
  data () {
    return {
      mainSRC: 'https://images-na.ssl-images-amazon.com/images/I/81zm9tKLsxL._SX450_.jpg',
      images: mockImages,
      searchText: ''
    }
  },
  methods: {
    loadImage: function() {
      return '../assets/jupiter.jpg'
    },
    setImage: function(tag) {
      this.mainSRC = tag
    },
    async searchAPI(searchText) {
          const response = await fetch(`https://images-api.nasa.gov/search?q=${searchText}&media_type=image`)
          const results = await response.json()
          this.mainSRC = results.collection.items[0].links[0].href
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
