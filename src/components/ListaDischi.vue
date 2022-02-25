<template>
    <div class="back">
        <div class="Cdisc">
            <div class="card" v-for="(disco, index) in dischiFiltrati" :key="index">
            <img :src="disco.poster">
            <h3>{{disco.title}}</h3>
            <span>{{disco.author}}</span>
            <span>{{disco.year}}</span>
        </div>
        </div>
    </div>
  
</template>

<script>

// integro axios 
const axios = require('axios');

export default {
     name:"listaDischi",
     props: {
         'selectedGnr': String
        },
     data() {
         return {
            ListaDischi: [],
            generi: []
        }
    },
    computed: {
        dischiFiltrati() {
            if (this.selectedGnr == '') {
                return this.ListaDischi;
            } else {
                return this.ListaDischi.filter( disc => {
                  return disc.genre == this.selectedGnr;

                });

            }
           
        }

    },
    
    methods: {
        getDischi() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.ListaDischi = response.data.response;
                
                this.ListaDischi.forEach(disc => {
                    if(!this.generi.includes(disc.genre)) {
                        this.generi.push(disc.genre);
                    }
                });

                this.$emit('listaGeneri', this.generi);



            })
        }
    },
    created() {
        this.getDischi();

    }

}
</script>

<style lang="scss">

.back {
    width: 100%;
    height: 100vh;
    background-color: #1e2d3b;
    
    .Cdisc {
    margin: 0 auto;
    width: 80%;
    display: flex;
    flex-wrap: wrap;
    }
}

.card {
    background-color: #2e3a46;
    border-radius: 10px;
    width:calc(90% / 5);
    height: 350px;
    margin:50px 10px;
    
    h3{
        color: white;
        text-align: center;
        font-size: 30px;
    }
    span {
        color: rgb(126, 125, 125);
        text-align: center;
    }
}


.card img {
    width: 150px;
    height: 150px;
    margin: 30px auto;
    border-radius: 10px;
}


</style>




