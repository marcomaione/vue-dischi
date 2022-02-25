<template>
  <div id="app">
    <myHeader :genresList="genresList" ></myHeader>
    <listaDischi @listaGeneri="setGenres"></listaDischi>
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

    }
  },
  methods: {
    setGenres(generiEvt) {
      this.genresList = generiEvt;

    }

  }
}
</script>

<style lang="scss">


</style>
