<script>
export default {
  data() {
    return {
      shopOnline: [
        {
          image: "buy-comics-digital-comics.png",
          sub: "lorem ipsum",
        },
        {
          image: "buy-comics-merchandise.png",
          sub: "lorem ipsum",
        },
        {
          image: "buy-comics-shop-locator.png",
          sub: "lorem ipsum",
        },
        {
          image: "buy-comics-subscriptions.png",
          sub: "lorem ipsum",
        },
        {
          image: "buy-dc-power-visa.svg",
          sub: "lorem ipsum",
        },
      ],
    };
  },
  methods: {
    getImagePath(image) {
      // Assuming your images are in the public directory
      return `src/assets/img/${image}`;
    },
  },
};
</script>

<template>

    <div class="banner">
        <ul>
            <li v-for="(image, index) in shopOnline" :key="index">
                <a href="">
                    <img :src="getImagePath(image.image)" :alt="image.alt">
                    <p></p>

                </a>
            </li>
        </ul>
        
    </div>

    

</template>

<style lang="scss">
@use "../style/partials/mixin" as *;

.banner {
    background-color: blue;
    color: white;
}

ul {
    @include flex();
    list-style: none;
    gap: 1rem;
    
    img {
        width: 100%;
    }
}

</style>