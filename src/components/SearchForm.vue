<template>
  <form class='search-form' v-on:submit.prevent='searchAPI(searchText)'>
      <input class='search-input' type='text'  v-model="searchText" placeholder='type a search' />
  </form>
</template>

<script>


export default {
  name: 'SearchForm',
  data () {
    return {
        searchText: ''
    }
  },
  methods: {
      searchAPI() {
          console.log(searchText)
      }
  },
}
</script>

<style scoped>
    .search-input {
        box-sizing: border-box;
        height: 40px;
        width: 300px;
        border-radius: 50px;
        border: 3px solid white;
        color: white;
        background-color: black;
        padding: 20px;
        font-size: 1.2rem;
    }
    .search-input::placeholder {
        color: white;
    }
</style>
