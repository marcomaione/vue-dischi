<template>
  <div id="app">
    <myHeader></myHeader>
    <listaDischi></listaDischi>
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
    
  }
}
</script>

<style lang="scss">


</style>
