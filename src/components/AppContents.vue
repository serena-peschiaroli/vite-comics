<script>
import CardComponents from './cardComponents.vue';
export default {
    components: {
        CardComponents,
    },


    data () {
        return{
            currentSeries: [
            {
                "thumb": "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                "price": "$19.99",
                "series": "Action Comics",
                "type": "comic book"
            },
            {
                "thumb": "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                "price": "$3.99",
                "series": "American Vampire 1976",
                "type": "comic book"
            },
            {
                "thumb": "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                "price": "$16.99",
                "series": "Aquaman",
                "type": "graphic novel"
            },
            {
                "thumb": "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                "price": "$2.99",
                "series": "Batgirl",
                "type": "comic book"
            },
            {
                "thumb": "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                "price": "$3.99",
                "series": "Batman",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                "price": "$2.99",
                "series": "Batman Beyond",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg/",
                "price": "$3.99",
                "series": "Batman/Superman",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                "price": "$4.99",
                "series": "Batman/Superman Annual",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                "price": "$5.99",
                "series": "Batman: The Joker War Zone",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                "price": "$6.99",
                "series": "Batman: Three Jokers",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                "price": "$4.99",
                "series": "Batman: White Knight Presents: Harley Quinn",
                "type": "comic book"
            },
            {
                "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
                "price": "$16.99",
                "series": "Catwoman",
                "type": "graphic novel"
            }
            ],
        };
    },
};
</script>

<template>
    <section>

    
        <div class="jumbotron">
            <a href="" class="btn btn-xl"> CURRENT SERIES</a>
            
            

        </div>
       <div class="container">
                <div class="row">
                    <CardComponents v-for="(item, index) in currentSeries" :key="index" :thumb="item.thumb" :series="item.series"/>

                </div>
                <a href="" class="btn btn-sm"> LOAD MORE </a>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;

section {
    background-color: black;
}
.jumbotron {
    min-height: 300px;
    background-image: url("../assets/img/jumbotron.jpg");
    background-size: cover;
    position: relative;
    
    
}

.container {
    padding: 3rem 0;
}
.row {
    
    

    @include flex(row, center, center, wrap);
    gap: 1rem;
    padding: 1rem 0;
    color: white;

    .col {
        width: calc(100%/5);
       
    }

    


}

.btn {
    display: flex;
    justify-content: center;
    align-self: center;
    background-color: rgb(59, 104, 162);
    text-decoration: none;
    color: white;
    padding: 1rem;
    width: 150px;
    text-align: center;
   
    margin: 0 auto;
    
}

.btn-xl {
    padding: 1rem;
    font-size: 18px;
    position:absolute;
    bottom: -1.8rem;
    width: 250px;
}


</style>