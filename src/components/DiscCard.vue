<template>
  <div class="card">
        <img :src="item.poster" :alt="item.title">
        <h3>{{ item.title }}</h3>
        <span>{{ item.author }} <br> {{ item.year }}</span>
  </div>
</template>

<script>


export default {
  name: 'DiscCard',

  props: {
    item : Object,
  },

  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .card {

        width: calc((100% /5) - 40px);
        margin: 0 20px;
        margin-bottom: 20px;
        padding: 20px;
        background-color: grey;
        text-align: center;

        img {
            width: 100%;
        }

        h3 {
            font-weight: 600;
            margin-top: 20px;
            color: white;
        }

        span {
            font-size: 12px;
            font-weight: 500;
        }
}
</style>