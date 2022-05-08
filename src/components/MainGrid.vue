<template>
<section class="container">
        <app-loader v-if="loading" />

        <div class="box" v-for="(disc) in discList" :key="disc.id">
            <app-card :item= "disc" />
        </div>

</section>
    
</template>

<script>
import AppLoader from './AppLoader.vue';
import AppCard from './AppCard.vue';
import axios from 'axios';


export default {
    name:'MainGrid',
    components: {
        AppCard,
        AppLoader,
        
    },
    data(){
        return {
            discList: [],
            apiDisc: 'https://flynn.boolean.careers/exercises/api/array/',
            loading: false,
        }
    },
    mounted() {
        this.loading = true;
        axios.get(this.apiDisc + 'music').then((res)=> {
            // console.log(res);
            this.discList = res.data.response;
            // console.log(this.discList)
            this.loading = false;
        }).catch((error)=> {
            console.log(error);
        })
    }
    
}
</script>

<style lang="scss">
@import '../style/variables';

main {
  height: calc(100% - 50px);
  background-color: $bgMain;
}

section.container {
    width: 50%;
    display: flex;
    flex-wrap: wrap;
    padding-top: 50px;
    .box {
        width: calc((100% / 5) - 20px);
        margin: 10px 10px 35px;
    }
}

</style>