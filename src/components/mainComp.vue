<template>
  <main>
    <div class="header d-flex justify-content-between align-items-center">
        <div class="logo d-flex align-items-center">
            <img src="../assets/img/spotify-logo.png" alt="">
        </div>

        <inputSelectComp @filter='genereToFilter'/>
    </div>

    <div class="container">
        <div class="cards d-flex row row-cols-5 justify-content-around">
        
            <cardComp 
                :key="index"
                v-for="(data, index) in genereMusicToSearch"
                :dataObject="data"
            />

        </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios'
import inputSelectComp from "./inputSelectComp.vue"
import cardComp from "./cardComp.vue"

export default {
    name: 'mainComp',
    components: { 
        cardComp,
        inputSelectComp,
    },

    data(){
        return{
            baseURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            datasMusic: [],
            genereMusicToSearch: ''
        }
    },

    mounted(){
        axios.get(this.baseURL)
        .then(response => {
        this.datasMusic = response.data.response;
        console.log(this.datasMusic);
        })
    },

    methods: {
        genereToFilter(selectedGenereToSearch){
            console.log(selectedGenereToSearch);
            this.genereMusicToSearch = selectedGenereToSearch;
        }
    },

    computed: {
        filteredMusic(){
            let datasMusicFiltered = [];
            if(this.genereMusicToSearch === 'All'){
                datasMusicFiltered = this.datasMusic;
            }
            else{
                datasMusicFiltered = this.datasMusic.filter(genere =>{
                    return genere.genre.toUpperCase().includes(this.genereMusicToSearch.toUpperCase());
                })
            }

            return datasMusicFiltered;
        }
    }

}

</script>

<style lang="scss" scoped>
    .header{
        height: 80px;
        background-color: #2b3844;

        .logo {
            height: 100%;
            margin-left: 25px;

            img{
                height: 90%;
            }
        }
    }
    

    main{
        height: calc(100% - 80px);
        background-color: #192a39;

        .card{
            background-color: #2b3844;
            height: 400px;
            width: calc(100% / 6);

            .img-album{
                height: 45%;
                width: calc(100% - 10px);

                img{
                    width: 100%;
                }
            }

            .info-album{
                .album-title{
                    color: white;
                }

                .cantante, .anno-album{
                    color: #787574;
                }
            }
        }
    }
</style>