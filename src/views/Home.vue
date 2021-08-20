<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <BannerStore/>

    <CategoryStore/>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import BannerStore from '../components/BannerStore.vue'
import CategoryStore from '../components/CategoryStore.vue'
export default {
  name: 'Home',
  components: {
    // HelloWorld
    BannerStore,
    CategoryStore
  }
}
</script>
