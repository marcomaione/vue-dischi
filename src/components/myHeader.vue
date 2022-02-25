<template>
<div class="ricerca">
    <div class="logo">
        <img src="https://cantabrialabsdifacooper.it/wp-content/uploads/2021/03/png-clipart-spotify-logo-spotify-computer-icons-podcast-music-apps-miscellaneous-angle-1-e1614848134495-300x300.png" alt="">
    </div>
    <div class="select">
        <select v-model="selectedGenre" @change="$emit('selectedGenreEvt', selectedGenre)">
            <option value="">seleziona un genere</option>
            <option v-for="(genre, index) in genresList" :value="genre" :key="index">{{genre}}</option>
        </select>
    </div>
    
</div>
  
</template>
<script>
export default {
    name:"myHeader",
    props: {
                'genresList':Array
            },
    data() {
        return {
            selectedGenre: ''
        }
    }

};
</script>

<style lang="scss">
.ricerca {
    height: 80px;
    width: 100%;
    background-color:#2e3a46;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .logo img {
    max-width: 50px;
    margin:15px 20px;
    }
    select {
    width: 200px;
    margin-right: 20px;
    }


}
</style>
