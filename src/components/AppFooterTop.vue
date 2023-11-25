<script>
import FooterComponents from './FooterComponents.vue';

export default {
    components: {
    FooterComponents,
    
},
    data() {
        return {
            // array x I col
            Item1: [
                {
                    title: "title1",
                    links: ["link1", "link2", "link3", "link4", "link5", "link6", "link7"],
                }
            ],
            // array x II col
            Item2: [
                {
                    title: "title2",
                    links: ["link1", "link2", "link3", "link4", "link5", "link6", "link7", "link8", "link9", "link10"],
                }
            ],
            // array x III col
            Item3: [
                {
                    title: "title3",
                    links: ["link1", "link2", "link3", "link4", "link5"],
                }
            ],
            // array x IV col
            Item4: [
                {
                    title: "title4",
                    links: ["link1", "link2"],
                }
            ],

            socialIcons: [ 
                {
                    name: "facebook", 
                    icon: "footer-facebook.png"
                },
                {
                    name: "periscope", 
                    icon: "footer-periscope.png"
                },
                {
                    name: "pinterest", 
                    icon: "footer-pinterest.png"
                },
                {
                    name: "twitter", 
                    icon: "footer-twitter.png"
                },
                {
                    name: "youtube", 
                    icon: "footer-youtube.png"
                },
                
            ]
        };
    },
};
</script>

<template>
    <div class="footer-top">
        <div class="container">
            <div class="row">
                <div class="sub-row">
                    <!-- renderizza I col -->
                    <div class="col">
                        <FooterComponents v-for="(item, index) in Item1" :key="index" :title="item.title" :links="item.links" />
                    </div>
                    <!-- renderizza II col -->
                    <div class="col">
                        <FooterComponents v-for="(item, index) in Item2" :key="index" :title="item.title" :links="item.links" />
                    </div>
                    <!-- renderizza III col -->
                    <div class="col">
                        <FooterComponents v-for="(item, index) in Item3" :key="index" :title="item.title" :links="item.links" />
                    </div>
                    <!-- renderizza IV col -->
                    <div class="col">
                        <FooterComponents v-for="(item, index) in Item4" :key="index" :title="item.title" :links="item.links" />
                    </div>
                </div>
                <div class="sub-row-1">
                    <div class="larger-col">
                        <!-- larger-col con img di bg -->
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="footer-bottom">
        <div class="btn">
            <a href="" class="btn login-btn">SIGN-UP NOW!</a>
        </div>
        <div class="nav-icons">
            <!-- Icone di navigazione renderizzate con props -->
            <FooterComponents :socialIcons="socialIcons"/>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;

//footer top generale
.footer-top {
    background-image: url("../assets/img/footer-bg.jpg");
    background-size: cover;
    background-position: center;
    color: white;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
}

//row che racchiude 2 sub-row

.row {
    @include flex();
    width: 80%;
    margin: 0 auto;
    justify-content: space-between;
}

//subrow con le .col
.sub-row {
    @include flex();
    flex-wrap: wrap;
    justify-content: flex-start;
    width: 30%;

    .col {
        width: calc(33.333% - 1rem);
        margin-top: 1rem;
        align-self: flex-start;

        &:last-child {
            margin-bottom: 0;
        }

        ul {
            list-style: none;
            li {
                margin-top: 0.5rem;
            }
        }
    }
}

//subrow per la .larger-col
.sub-row-1 {
    width: 60%;

    .larger-col {
        min-height: 400px;
        flex-grow: 1;
        display: flex;
        align-items: center;
        background-image: url(../assets/img/dc-logo-bg.png);
        background-size: cover;
        background-position: center;
        overflow: hidden;
    }
}

//bottom footer con btn
.footer-bottom {
    @include flex(row, space-between, center, nowrap);

    background-color: rgb(26, 25, 25);
    padding: 2rem;

    .login-btn {
        border: 2px solid blue;
    }

   

}



</style>
