<script>
export default {
    data() {
        return{};
    },
};
</script>

<template>
<div class="footer-top">
    <div class="container">

    
        <div class="row">
            <div class="col">
                <h4> Lorem </h4>
            </div>
            <div class="col">
                <h4> Lorem </h4>
            </div>
            <div class="col">
                <h4> Lorem </h4>
            </div>
            <div class="larger-col">
                <img src="../assets/img/dc-logo-bg.png" alt="">
            </div>
        </div>

        <div class="sub row">
        <div class="col">
            <h4> Lorem </h4>
        </div>
        </div>
   </div>
</div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
.footer-top {
    background-image: url("../assets/img/footer-bg.jpg");
    background-size: cover;
    background-position: center;
    height: 30em;
    color: white;

    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.row {
    @include flex();
    width: 100%;
    gap: 1rem;

    .col {
        flex: 1 0 calc(13.333% - 1rem);
        margin-bottom: 1rem;
        align-self: flex-start; 

        &:last-child {
            margin-bottom: 0;
        }
    }

    .larger-col {
        flex: 1 0 50%;
        display: flex;
        align-items: center;

        img {
            width: 80%;
            margin: auto;
            display: block;
        }
    }
}

</style>