<template>
        <div class="discs_list">
            <DiscCard v-for="(song, index) in detailsDiscs" :key="index" :item="song" />
        </div>
</template>

<script>
import axios from "axios";
import DiscCard from './DiscCard.vue';

export default {
  name: 'DiscsList',

  components: {
    DiscCard,
  },

  data(){
      return {
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          detailsDiscs: [],
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
