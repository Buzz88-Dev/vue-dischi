<template>
    <div class="selectSong">
        <div>
            <h3>Usa la Select per filtrare per genere</h3>
            <select v-model="selected" @change="sendValueSelect">
                <option v-for="(value, index) in itemGenre" :key="index">{{ value }}</option>
            </select>
        </div>

        <!-- <div>
            <h3>Usa l'input per cercare la tua canzone</h3>
            <button @click.prevent="resetSearch()">Clear</button>
            <button @click.prevent="$emit('mySearch', inputText)">Search</button>
            <input type="text" placeholder="Search" 
                v-model="inputText" 
                @keyup.enter="$emit('mySearch', inputText)">
                @keyup.enter="search()">
        </div> -->
    </div>
</template>

<script>
export default {
    name: 'SelectSongGenre',

    props: {
        itemGenre : Array,   
    },

    data(){
        return {
            inputText : "",
            selected: 'All',           
        }
    },

    methods: {
        resetSearch(){
            this.inputText = "";
            this.$emit('mySearch', this.inputText)
            // this.search();
        },

        // search(){
        //     this.$emit('mySearch', this.inputText);
        // }

        sendValueSelect() {
            this.$emit('mySelect', this.selected);
        }
    }
}
</script>

<style  scoped lang="scss">

    .selectSong {
        padding: 20px;
        text-align: center;
        display: flex;
        justify-content: center;

        h3 {
            color: white;
            margin-bottom: 20px;
        }

        button {
            margin: 0px 30px;
        }
    }
    
</style>