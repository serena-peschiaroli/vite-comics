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
          image: "buy-comics-subscriptions.png",
          sub: "lorem ipsum",
        },
        {
          image: "buy-comics-shop-locator.png",
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
    
      return `src/assets/img/${image}`;
    },
  },
};
</script>

<template>

    <div class="banner">
        <ul>
            <li v-for="(image, index) in shopOnline" :key="index">
                <a class="item-link" href="">
                    <img :src="getImagePath(image.image)" :alt="image.alt">
                    <p> {{  image.sub }}</p>

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
    height: 6rem;
    padding: 1.5rem
}

ul {
  @include flex();
  list-style: none;
  gap: 1.5rem;

  li {
    flex: 0 0 auto; 
  }

  .item-link {
    @include flex();
    a{
        text-decoration: none;
    }
    p {
        color: white;
        text-decoration: none;
        margin-left: 1rem
    };
    

    img {
      width: 2rem;
    }

  }
}
</style>