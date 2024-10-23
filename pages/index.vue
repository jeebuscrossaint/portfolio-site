<template>
    <div class="flex items-center justify-center h-screen bg-gray-200">
      <card :text="'Hello World'" :bgColor="'black'" />      
      <card :text="'Hi Mom!'" :bgColor="'red            '" />

      <a :href="githubProfile.html_url" target="_blank" v-if="githubProfile" class="absolute top-0 left-0 m-4 bg-gray-800 rounded shadow-lg text-white flex items-center p-4 no-underline">
        <img :src="githubProfile.avatar_url" :alt="githubProfile.login" class="w-12 h-12 rounded-full mr-4">
        <p>{{ githubProfile.login }}</p>
      </a>
      <div class="absolute top-0 left-1/2 transform -translate-x-1/2 m-4 bg-gray-800 rounded shadow-lg text-white p-4">
        <p>Amarnath Patel</p>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios' 
  
  export default {
    data() {
      return {
        githubProfile: null
      }
    },
    created() {
      axios.get('https://api.github.com/users/jeebuscrossaint')
        .then(response => {
          this.githubProfile = response.data
        })
    }
  }
  </script>
  
  