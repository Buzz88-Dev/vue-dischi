<template>
      <div v-if="loading">
            <LoadDiscs />
      </div>
      <div v-else class="discs_list">
            <DiscCard v-for="(song, index) in detailsDiscs" :key="index" :item="song" />
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
        this.detailsDiscs = result.data.response;
        this.loading = false;
        console.log(result);
        console.log(result.data);
        console.log(this.detailsDiscs);
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

  .discs_list {
    width: 100%;
    background-color: rgb(33, 39, 65);
    display: flex;
    flex-wrap: wrap;
    // debug
    height: 600px;   
  }

</style>
