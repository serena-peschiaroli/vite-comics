<script>
export default {
  data() {
    return {
      // Inizializza un array con immagini e descrizioni per lo shopping online
      shopOnline: [
        {
          image: "buy-comics-digital-comics.png",
          sub: "lorem ipsum",
          isActive: false,
        },
        {
          image: "buy-comics-merchandise.png",
          sub: "lorem ipsum",
          isActive: false,
        },
        {
          image: "buy-comics-subscriptions.png",
          sub: "lorem ipsum",
          isActive: false,
        },
        {
          image: "buy-comics-shop-locator.png",
          sub: "lorem ipsum",
          isActive: false,
        },
        {
          image: "buy-dc-power-visa.svg",
          sub: "lorem ipsum",
          isActive: false,
        },
      ],
    };
  },
  methods: {
     // Metodo per ottenere il percorso completo dell'immagine
    getImagePath(image) {
    
      return `src/assets/img/${image}`;
    },
    setActive(index) {
      // iterare attraverso foreach
      this.shopOnline.forEach((image, i) => {
        //funzione di callback eseguita per ogni item;
        //x ogni item isacrive = true se i combacia con index
        image.isActive = i === index;
      });
    }
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
                  <a class="item-link" :class="{active: image.isActive}" :href="''" @mouseover="setActive(index)">
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
    height: 6rem;
    padding: 1.5rem
}

ul {
  @include flex();
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
    }
  }
}

</style>