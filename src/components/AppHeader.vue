<script>
export default {
    data() {
        // Definisci un array di elementi di navigazione
        return {
            navItems : [
                {
                    title: "PERSONAGGI",
                    isActive: false,
                },
                {
                    title: "COMICS",
                    isActive: false,
                },
                {
                    title: "FILM",
                    isActive: false,
                },
                {
                    title: "TV",
                    isActive: false,
                },
                {
                    title: "GIOCHI",
                    isActive: false,
                },
                {
                    title: "COLLEZIONABILI",
                    isActive: false,
                },
                {
                    title: "VIDEO",
                    isActive: false,
                },
                {
                    title: "FAN",
                    isActive: false,
                },
                {
                    title: "NOTIZIE",
                    isActive: false,
                },
                {
                    title: "NEGOZIO",
                    isActive: false,
                },
            ]
        };
    },
    methods: {
        setActive(item) {
            this.navItems.forEach((navItem, index) => {
                item.isActive = navItem === index;
            });
        }
    }
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
                            <!-- Collegamento con classe "active" se l'elemento è attivo -->
                            <a href="#" class="nav-link">{{ item.title }}</a>
                            <!-- <a :class="{active: item.isActive}" href="#" @mouseover="setActive(item)"> {{ item.title }}</a> -->
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

// header {
//   .header-top {
//     height: 3rem;
//     background-color: black;
//   }

//   .nav {
//     @include flex(row, space-between, center, nowrap);

//     ul {
//       @include flex(row, flex-end, center, nowrap);
//       gap: 1rem;
//       list-style: none;

//       li {
//         position: relative;

//         a {
//           text-decoration: none;
//           position: relative;

//           &:after {
//             content: "";
//             position: absolute;
//             bottom: 0;
//             left: 50%;
//             transform: translateX(-50%);
//             width: 0;
//             height: 2px;
//             background-color: blue;
//             transition: width 0.3s ease;
//           }

//           &.active:after {
//             width: 100%;
//           }
//         }
//       }
//     }
//   }
// }






</style>
