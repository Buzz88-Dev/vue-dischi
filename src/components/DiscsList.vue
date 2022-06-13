<template>
  <div class="container">
    <div v-if="loading">
            <LoadDiscs />
    </div>
    <div v-else class="discs_list">
            <DiscCard v-for="(song, index) in detailsDiscs" :key="index" :itemDiscCard="song" /> 
                                                <!-- itemDiscCard è quello indicato in props in DiscCard.vue mentre song in DiscsList.vue -->
    </div>
  </div>
</template>

<script>
import axios from "axios";
import DiscCard from './DiscCard.vue';
import LoadDiscs from './Load.vue';

export default {
  name: 'DiscsList',

  components: {
    DiscCard,
    LoadDiscs,
  },

  data(){
      return {
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          detailsDiscs: [],
          loading: true,
      }
  },

  created(){
    this.getDiscs();
  },

  methods : {
    getDiscs() {
      axios
      .get(this.apiUrl)
      .then((result) => {
        this.detailsDiscs = result.data.response;  // è un array composto da 10 oggetti
                                                   // (10) [{…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}]
        this.loading = false;
        console.log(result);
        console.log(result.data);
        console.log(this.detailsDiscs);
        console.log(this.loading);
      })
      .catch((error) => {
        console.log("Errore", error);
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  .container {
    background-color: rgb(33, 39, 65);
    padding-top: 40px;
    padding-bottom: 20px;
  }
  .discs_list {
    width: 80%;
    display: flex;
    flex-wrap: wrap;
    margin: auto;
    color: white;
  }

</style>
