<script>
export default {
    props:{
        img:String,
        title:String,
        type:String
    }
}
</script>
<template>
    <div class="card">
        <img :src="img">
        <h4>{{ title }}</h4>
        <p>{{ type }}</p>
    </div>
</template>
<style lang="scss">
    .card{
        background-color: orange;
        width: 100px;
        text-align: center;
        img {
            width: 100%;
        }
    }
</style>