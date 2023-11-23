<script>
export default {
    data() {
        return{
            navItems : [
                {
                    title: "CHARACTES",
                    isActive: false,
                },
                {
                    title: "COMICS",
                    isActive: false,
                },
                {
                    title: "MOVIES",
                    isActive: false,
                },
                {
                    title: "TV",
                    isActive: false,
                },
                {
                    title: "GAMES",
                    isActive: false,
                },
                {
                    title: "COLLECTIBLES",
                    isActive: false,
                },
                {
                    title: "VIDEOS",
                    isActive: false,
                },
                {
                    title: "FANS",
                    isActive: false,
                },
                {
                    title: "NEWS",
                    isActive: false,
                },
                {
                    title: "SHOP",
                    isActive: false,
                },
            ]
        };
    },
};
</script>

<template>

    <header>
        
        <div class="logo">
            <img src="../assets/img/dc-logo.png" alt="">
        </div>
       
       
        <nav>
            <ul>
                <li v-for="item in navItems" :key="item.title">
                        <a :class="{active: item.isActive}" href=""> {{ item.title }}</a>

                </li>
            </ul>
        </nav>
        
        
        
        
        
    </header>

</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
header {
    @include flex_bn();
    height: 6rem;
    padding: 1rem;
    
    color: black;
    img {
        width: 60px;
    }
   
    

}


ul {
    
    @include flex();
    font-size: 0.7rem;
    list-style: none;
    
    a {
        text-decoration: none;
        color: black;
        padding: 1rem;


        &.active {
            border-bottom: 1px solid blue;
        }
    }
}

</style>