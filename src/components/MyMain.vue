<template>
    <div class="container">
        <div class="row row-cols-2 row-cols-sm-3 row-cols-lg-5 justify-content-center">
            <Album
            v-for="(album, indice) in listaAlbum" 
            :key="indice"
            :album="album"
            >
            </Album>
        </div>
</div>
</template>

<script>
    //integrazione di axios
    const axios = require('axios');
    import Album from './partials/Album.vue'

export default {
    name: 'MyMain',
    data(){
        return{
            listaAlbum: []
        }
    },
    components:{
        Album,
    },
    methods:{
        getAlbum(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                // successo
                this.listaAlbum = response.data.response;
                console.log(response);
            })
            .catch(function (error) {
                // errore
                console.log(error);
            })
            .then(function () {
                //  eseguito
            });
        }
    },
    created(){
        this.getAlbum();
    }
}
</script>

<style scoped lang="scss">
 @import "../assets/style/generale.scss";
  @import "../assets/style/variabili.scss";
</style>