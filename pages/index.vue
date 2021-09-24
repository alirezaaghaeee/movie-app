<template>
  <div class="home">
    <Hero />
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      movies: [],
    }
  },
  async fetch(){
    await this.getmovie()
  },
  methods: {
    async getmovie() {
      const data = axios.get(
        'https://api.themoviedb.org/3/movie/now_playing?api_key=def5785d32d90d07ffbece2bba421a78&language=en-US&page=1'
      )
      const result=await data;
      console.log(result.data);
    },
  },
}
</script>

<style lang="scss" scoped>
</style>