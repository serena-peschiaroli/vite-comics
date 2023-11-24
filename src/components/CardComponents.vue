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
        <img :src="thumb" alt="">
        <h5> {{ series }} </h5>


    </div>
    

                

</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
.card{
   

    img {
                
        width: 200px;
        height: 200px;
        aspect-ratio: 1;
    }

    h5 {
        width: 200px;
        margin-top: 0.5rem;
        margin-bottom: 0.5rem;
        color: white;
        text-align: start;
        
    }

        

           

}

</style>