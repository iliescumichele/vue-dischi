<template>
  <main>
    <div class="container">
        <div class="cards d-flex row row-cols-5 justify-content-around">
        
            <cardComp />

        </div>
    </div>
  </main>
</template>

<script>
import cardComp from "./cardComp.vue"

export default {
    name: 'mainComp',
    components: { cardComp }
}
</script>

<style lang="scss" scoped>
    main{
        height: calc(100% - 100px);
        background-color: #192a39;
    }


    .card{
        background-color: #2b3844;
        height: 400px;
        width: calc(100% / 6);

        .img-album{
            background-color: red;
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
</style>