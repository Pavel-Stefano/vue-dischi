<template>
    <section class="container">
        <app-loader v-if="loading" />

        <search-component :discGenre="genre" @mySearch="setSearchText($event)"  />

        <div class="box" v-for="(disc) in filteredList" :key="disc.id">
            <app-card :item= "disc" />
        </div>

    </section>
    
</template>

<script>
import AppLoader from './AppLoader.vue';
import AppCard from './AppCard.vue';
import SearchComponent from './SearchComponent.vue';
import axios from 'axios';



export default {
    name:'MainGrid',
    components: {
        AppCard,
        AppLoader,
        SearchComponent,
        
    },
    data(){
        return {
            discList: [],
            apiDisc: 'https://flynn.boolean.careers/exercises/api/array/',
            loading: false,
            genre: [],
            searchText:'',
        }
    },
    methods: {
        setSearchText(testo){
            this.searchText = testo;
            console.log(this.searchText, 'searchText')
        }
    },
    computed: {
        filteredList(){
            
            if(this.searchText === '') return this.discList;
            return this.discList.filter((disc)=>{
                return disc.genre === this.searchText;
            })
            
        },
        

    },
    mounted() {
        this.loading = true;
        axios.get(this.apiDisc + 'music').then((res)=> {
            // console.log(res);
            this.discList = res.data.response;
            // console.log(this.discList)
            this.discList.forEach((el)=> {
                if(!this.genre.includes(el.genre)) {
                    this.genre.push(el.genre);
                }
            })
            console.log(this.genre)
            this.loading = false;
        }).catch((error)=> {
            console.log(error);
        })
    },
    
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