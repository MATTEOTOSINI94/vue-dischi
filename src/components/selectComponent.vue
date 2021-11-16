<template>
<div class="pt-3">
    <select id="select-style" @change="$emit('searchGenre', sell)" v-model="sell" class="form-select" aria-label="Default select example">
                <option value="all">Tutti generi</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jezz</option>
                <option value="Metal">Metal</option>
            </select>
             </div>
</template>

<script>
export default {
    name:"SelectBar",

    data(){
        return{
         sell:"all"
        }
    }

}
</script>

<style lang="scss" scoped>
    #select-style{
       
        width: 200px;
    }
</style>