<script>
export default {
  data() {
    return {
      // Inizializza un array con immagini e descrizioni per lo shopping online
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
     // Metodo per ottenere il percorso completo dell'immagine
    getImagePath(image) {
    
      return `src/assets/img/${image}`;
    },
    
  },
};
</script>

<template>
  
<!-- striscia con imgs e link cliccabili -->
    <div class="banner">
      <div class="container">

      
          <ul>
            <!-- Itera elementi -->
              <li v-for="(image, index) 
              in shopOnline" :key="index">
                  <a class="item-link"  :href="''">
                    <!-- Immagine con percorso dinamico -->
                      <img :src="getImagePath(image.image)" :alt="image.alt">
                      <p> {{  image.sub }}</p>

                  </a>
              </li>
          </ul>
      </div>  
    </div>

    

</template>

<style lang="scss" scoped>
/* Utilizza uno stile mixin per le proprietà flexbox */
@use "../style/partials/mixin" as *;

.banner {
    background-color: blue;
    color: white;
    height: 8rem;
    padding: 2rem
    
}

ul {
  @include flex(row, center, center, nowrap);
  list-style: none;
  gap: 1.5rem;

  li {
    flex: 0 0 auto;

    .item-link {
      @include flex();
      text-decoration: none;

      p {
        color: white;
        text-decoration: none;
        margin-left: 1rem;
      }

      img {
        width: 2rem;
      }

      &:hover {
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.8);
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.8);
      border-bottom: 2px solid white; 
    }
    
  }
}
}

</style>