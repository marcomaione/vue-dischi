<template>
  <div id="app">
    <myHeader @selectedGenreEvt="selectedGnr" :genresList="genresList" ></myHeader>
    <listaDischi @listaGeneri="setGenres" :selectedGnr="selectedGnr"></listaDischi>
  </div>
</template>

<script>
import myHeader from './components/myHeader.vue';
import listaDischi from './components/listaDischi.vue';


export default {
  name: 'App',
  components: {
    myHeader,
    listaDischi,
    
  },
  dat() {
    return {
      genresList: [],
      selectedGnr:''

    }
  },
  methods: {
    setGenres(generiEvt) {
      this.genresList = generiEvt;

    },
    setSelectedGnr(selectedGenreEvt) {
      this.selectedGnr = selectedGenreEvt;

    }

  }
}
</script>

<style lang="scss">


</style>
