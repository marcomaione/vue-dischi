<template>
<div class="ricerca">
    <div class="logo">
        <img src="https://cantabrialabsdifacooper.it/wp-content/uploads/2021/03/png-clipart-spotify-logo-spotify-computer-icons-podcast-music-apps-miscellaneous-angle-1-e1614848134495-300x300.png" alt="">
    </div>
    <div class="list">
        <SelectDischi></SelectDischi>
    </div>
    
</div>
  
</template>
<script>
import SelectDischi from './SelectDischi.vue'
export default {
    name:"myHeader",
    components: {
        SelectDischi,
    },

}
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


}
</style>
<SelectDischi></SelectDischi>