<template>
    <div class="list">

    </div>
  
</template>

<script>

// integro axios 
const axios = require('axios');
export default {
     name:"ListaDischi",
     data() {
         return {
             listaDischi: []
        }
    },
    methods: {
        getDischi() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.listaDischi = response.data;
                console.log(response);

            })
        }
    },
    created() {
        this.getDischi();

    }

}
</script>

<style lang="scss">
.list {
    min-height: 100vh;
    background-color:#1e2d3b ;
}
</style>

