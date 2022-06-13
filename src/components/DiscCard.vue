<template>
  <div class="card">
        <img :src="itemDiscCard.poster" :alt="itemDiscCard.title">
        <div class="text">
            <h4>{{itemDiscCard.title}}</h4>
            <div class="author_year">
                <div>
                    {{itemDiscCard.author}}
                </div>
                <div>
                    {{itemDiscCard.year}}
                </div>
            </div>
        </div>
  </div>
</template>

<script>


export default {
  name: 'DiscCard',

  props: {
    itemDiscCard : Object,   
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .card {

        width: calc((100% /5) - 40px);
        margin: 0  20px 20px 20px;
        padding: 20px;
        background-color: rgba(46,58,70,255);
        text-align: center;

        img {
            width: 100%;
            height: auto;
        }

        .text {
          display: flex;
          flex-direction: column;
          align-items: center;
          padding: 10px;
        }

        h4 {
            display: flex;
            flex-wrap: wrap;
            text-align: center;
            text-transform: uppercase;
        }
        .author_year {
            color: grey;
            text-align: center;
            padding-top: 10px;
            font-size: 12px;
        }
}
</style>