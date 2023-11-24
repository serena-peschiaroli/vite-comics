<script>
export default {
    data() {
        // Definisci un array di elementi di navigazione
        return {
            navItems : [
                {
                    title: "PERSONAGGI",
                },
                {
                    title: "COMICS",
                },
                {
                    title: "FILM",
                },
                {
                    title: "TV",
                },
                {
                    title: "GIOCHI",
                },
                {
                    title: "COLLEZIONABILI",
                },
                {
                    title: "VIDEO",
                },
                {
                    title: "FAN",
                },
                {
                    title: "NOTIZIE",
                },
                {
                    title: "NEGOZIO",
                },
            ]
        };
    },
  
};
</script>

<template>
    <!-- Template per l'intestazione con logo e menu di navigazione -->
    <header>
        <div class="header-top">

        </div>
        <div class="container">
            <div class="nav">
                <div class="logo">
                        <img src="../assets/img/dc-logo.png" alt="Logo DC">
                </div>  

                <!-- Menu di navigazione -->
                <div class="nav-links">
                    <ul>
                        <!-- Itera sugli elementi di navigazione -->
                        <li v-for="(item, index) in navItems" :key="item.title">
                            
                            <a href="#" class="nav-link">{{ item.title }}</a>
                        
                        </li>
                    </ul>
                </div>
            </div> 
        </div>
       
        
       
      
    </header>
</template>

<style  lang="scss" scoped>
/* Utilizza uno stile mixin per le proprietà flexbox */
@use "../style/partials/mixin" as *;


header {
  .header-top {
    height: 3rem;
    background-color: black;
  }

  .nav {
    @include flex(row, space-between, center, nowrap);

    ul {
      @include flex(row, flex-end, center, nowrap);
      gap: 1rem;
      list-style: none;

      li {
        position: relative;

        .nav-link {
          text-decoration: none;
          position: relative;

          &:hover:after {
            content: "";
            position: absolute;
            bottom: -3rem;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            height: 2px;
            background-color: blue;
            transition: width 0.3s ease;
          }
        }
      }
    }
  }
}


</style>
