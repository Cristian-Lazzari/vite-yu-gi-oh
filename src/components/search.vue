<script>
import axios from 'axios'
import { state } from '../state'
export default {
    data(){
        return{
            arrarktype:[],
            state,

        }
    },
    methods: {
        arktypefoo(){
            axios
            .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then(output => this.arrarktype = output.data)
        }
    },
    created(){
        this.arktypefoo()
    },
    
}
</script>
<template >
    <div>
        <select v-model="state.choise" @change="$emit('choise')">
            <option
            v-for="item in arrarktype"
            :key="item.id" 
            :value="item.archetype_name">
                {{ item.archetype_name }}
            </option>
        </select>
        <button @click="$emit('choise')"> heyy </button>
    </div>
</template>
<style lang="scss" scoped>
    div{
        padding: 2rem;
    }
    button{
        width: 30px;
        margin-left: 2rem;
    }
</style>