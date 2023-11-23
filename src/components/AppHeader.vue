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
        setActive(index) {
            this.navItems.forEach((item, i) => {
                item.isActive = i === index;
            });
        }
    }
};
</script>

<template>
    <!-- Template per l'intestazione con logo e menu di navigazione -->
    <header>
        <!-- Logo -->
        <div class="logo">
            <img src="../assets/img/dc-logo.png" alt="Logo DC">
        </div>
       
        <!-- Menu di navigazione -->
        <nav>
            <ul>
                <!-- Itera sugli elementi di navigazione -->
                <li v-for="item in navItems" :key="item.title">
                    <!-- Collegamento con classe "active" se l'elemento è attivo -->
                    <a :class="{active: item.isActive}" href="" @mouseover="setActive(index)"> {{ item.title }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style  lang="scss">
/* Utilizza uno stile mixin per le proprietà flexbox */
@use "../style/partials/mixin" as *;

header {
    /* Applica stili flexbox all'intestazione */
    @include flex_bn();
    height: 6rem;
    padding: 1rem;
    color: black;
    
    /* Stili per il logo */
    img {
        width: 60px;
    }
}

ul {
    /* Applica stili flexbox alla lista di navigazione */
    @include flex();
    font-size: 0.7rem;
    list-style: none;
    
    a {
        /* Rimuove la sottolineatura dai collegamenti */
        text-decoration: none;
        color: black;
        padding: 1rem;

        /* Stili per l'elemento di navigazione attivo */
        &.active {
            border-bottom: 1px solid blue;
        }
    }
}
</style>
