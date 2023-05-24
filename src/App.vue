<script >
import search from './components/search.vue';
import cardlist from './components/cardlist.vue';
import { state } from './state';
import axios from 'axios';

export default{
    data(){
        return{
            state,
            ciao:[]
        }
    },
    components:{ search, cardlist},
    methods: {
        axiosSerch(){
            axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php',{
                params:{
                    num: '20',
                    offset: '0',
                }
            })
            .then(renspose => this.state.listCard = renspose.data.result);
            console.log('il mio array',  this.state.listCard)
        }
    },
    created(){
        this.axiosSerch()
    }

}
</script>

<template>
    <header>
        <h1>Yu-gi-ho Api</h1>
    </header>
    <main>
        <search />
        <cardlist />

    </main>
</template>

<style lang="scss">
    @use './assets/styles/general.scss' as *;
    header{
        padding: 1rem;
    }
    main{
        background-color: orange;
    }
</style>
