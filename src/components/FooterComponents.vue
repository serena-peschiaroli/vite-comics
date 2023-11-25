<script>
export default {
    props: {
        title: String,
        links: Array,
        socialIcons: Array,
    },
    methods: {
        getImagePath(icon) {
            return `src/assets/img/${icon}`;
        }

    }
};
</script>

<template>
  
        <h3> {{ title }} </h3>
        <ul>
            <li v-for="item in links" :key="item"> {{ item }} </li>
        </ul>

        <!-- Renderizzare icone social con immagini dinamiche -->

        <div class="nav-icons">

            
                <a href="#" class="social-icon">

            
                    <img v-for="(socialIcon, index) in socialIcons" :key="index" :src="getImagePath(socialIcon.icon)" alt="socialIcon.name" />
                </a>
        </div>
   
</template>

<style lang="scss" scoped>

@use "../style/partials/mixin" as *;


        
    
ul {
    list-style: none;
    li {
        margin-top: 0.5rem;
    }
}


a {
    text-decoration: none;

    img {
        &:hover{
        background-color: rgba(255, 255, 255, 0.2);
        border-radius: 50%;
        }
    }
    

}
.nav-icons {
        @include flex();
        gap: 1rem;
        .social-icon{
            @include flex();
            gap: 1rem;
            
            
            
            

        }
        
    
    }


</style>