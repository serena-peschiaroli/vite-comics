<script>
export default{
    props: {
        thumb: String,
        series: String,
    }
}
</script>

<template>
    
                    <div class="card">
                        <img :src="thumb " alt="">
                        <h3> {{ series }} </h3>


                    </div>
                

</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
.card{
    height: 100%;

            img {
                width: 100%;
                max-width: 150px;
            }
}



</style>