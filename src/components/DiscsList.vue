<template>
  <div class="discs_list">

  </div>
</template>

<script>
export default {
  name: 'DiscsList',

  components: {

  },

  data(){
      return {
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          detailsDiscs: [],
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  .discs_list {
    width: 100%;
    background-color: rgb(33, 39, 65);
    // debug
    height: 600px;   
  }
</style>
