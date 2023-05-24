<script>
import card from './card.vue'
import { state } from '../state'
export default {
    data(){
        return{
            state,
        }
    },
    components:{ card }
}
</script>
<template>
    <div class="card-container">
        <card 
        v-for="item in state.listCard" 
        :key="item.id"
        :img="item.card_images[0].image_url"
        :title="item.name"
        :type="item.archetype"
        />
    </div>
</template>
<style lang="scss">
   @use '../assets/styles/general.scss' as *;

   .card-container{
    padding: 2rem;
    background-color: azure;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
   }
</style>