<script >
import AppHeader from "./components/AppHeader.vue";
import AppContents from "./components/AppContents.vue";
import AppBanner from "./components/AppBanner.vue";
import AppFooterTop from "./components/AppFooterTop.vue";



export default {
  components: {
    AppHeader,
    AppContents,
    AppBanner,
    AppFooterTop,
    
}
}

</script>

<template>
  <AppHeader />
  <AppContents />
  <AppBanner />
  <AppFooterTop />
  
  
</template>

<style lang="scss">
@use "./style/general.scss"

</style>
