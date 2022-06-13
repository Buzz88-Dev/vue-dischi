<template>
    <div class="selectSong">
        <h3>FILTRA PER TIPO</h3>
        <select>
            <option value="0">all</option>
            <option value="1">Rock</option> 
            <option value="2">Pop</option> 
            <option value="3">Jazz</option>
            <option value="3">Metal</option>
        </select>
        <button id="mybutton">Click</button>
        <input type="text" placeholder="Search" 
            v-model="inputText" 
            @keyup-enter="$emit('mySearch', inputText)">
    </div>
</template>

<script>
export default {
    name: 'SelectSongGenre',

    data(){
        return {
            inputText : "",
        }
    }
}
</script>

<style  scoped lang="scss">

    .selectSong {
        padding: 20px;
        text-align: center;

        h3 {
            color: white;
            margin-bottom: 20px;
        }

        button {
            margin: 0px 30px;
        }
    }
    
</style>