<template>
<div class="container">
    <select name="select" id="select" v-model="inputText" @change="changeSearch">
        <option value="">All</option>
        <option :value="genre" v-for="(genre, index) in discGenre" :key="index">{{genre}}</option>

    </select>
</div>
    
</template>

<script>
export default {
    name:'SearchComponents',
    data() {
        return {
            inputText: '',
        }
    },
    props: ['discGenre'],
    
    methods: {
       changeSearch(){
           this.$emit('mySearch', this.inputText)
       }
    },
}


</script>

<style lang="scss" scoped>

</style>