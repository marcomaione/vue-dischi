<template>
    <div class="list">
        <div class="row">
            <div class="col" v-for="(disco, index) in listaDischi" :key="index">
                <img :src="disco.poster" alt="">
                <h2>{{disco.title}}</h2>
                <h4>{{disco.author}}</h4>
                <h6>{{disco.year}}</h6>
            </div>
        </div>

    </div>
  
</template>

<script>

// integro axios 
const axios = require('axios');
export default {
     name:"listaDischi",
     data() {
         return {
             listaDischi: [],
             loading:true,
        }
    },
    methods: {
        getDischi() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.listaDischi = response.data;
                this.loading = false;
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

