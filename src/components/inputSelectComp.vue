<template>
  <div class="">
        <select v-model="selected" @change="$emit('filter', selected)">
            <option disabled value >Seleziona genere musicale</option>
            <option >All</option>
            <option >Rock</option>
            <option >Pop</option>
            <option >Jazz</option>
            <option >Metal</option>
        </select> 
  </div>
</template>

<script>
export default {
    name: 'inputSelectComp',
    
    data(){
        return{
            selected: '',
        }
    }
}
</script>

<style lang="scss" scoped>
    select{
        margin-right: 25px;
        text-align: center;
        width: 250px;   

    }
</style>