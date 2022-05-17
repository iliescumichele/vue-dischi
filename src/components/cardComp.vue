<template>
  <div class="card mx-2 my-4 d-flex ">
    <div class="img-album my-3">
        <img :src="dataObject.poster" :alt="dataObject.title">
    </div>
    <div class="info-album text-center">
        <p class="album-title my-2 ">{{dataObject.title}}</p>
        <p class="cantante my-1 ">{{dataObject.author}}</p>
        <p class="anno-album">{{dataObject.year}}</p>
    </div>
  </div>
</template>

<script>
export default {
    name: 'cardComp',
    props: {
        dataObject : Object
    }
}
</script>

<style lang="scss" scoped>
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
</style>