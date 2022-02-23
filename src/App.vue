<template>
  <div id="app">
    <myHeader></myHeader>
    <ListaDischi></ListaDischi>
  </div>
</template>

<script>
import myHeader from './components/myHeader.vue';

import ListaDischi from './components/ListaDischi.vue';


export default {
  name: 'App',
  components: {
    myHeader,
    ListaDischi,
    
  }
}
</script>

<style lang="scss">


</style>
