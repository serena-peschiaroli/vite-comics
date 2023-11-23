<script>
export default {
    data() {
        return{};
    },
};
</script>

<template>
<div class="footer-top">
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
    </div>

    <div class="row">
      <div class="col">
        <h4> Lorem </h4>
      </div>
    </div>

</div>
</template>

<style lang="scss">
@use "../style/partials/mixin" as *;
.footer-top {
    background-image: url("../assets/img/footer-bg.jpg");
    background-size: cover;
    background-position: center;
    height: 6rem;
    color:white;
}
.row {
    @include flex_bn;
    width: 40%;
    .col{
        width: calc(100%/3);
    }

}

</style>