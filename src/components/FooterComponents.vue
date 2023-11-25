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
        <img v-for="(socialIcon, index) in socialIcons" :key="index" :src="getImagePath(socialIcon.icon)" alt="socialIcon.name" class="social-icon" />


   
</template>

<style lang="scss" scoped>

@use "../style/partials/mixin" as *;


        
    
ul {
    list-style: none;
    li {
        margin-top: 0.5rem;
    }
}

.social-icon {
    margin-right: 0.5rem;
        
}


</style>