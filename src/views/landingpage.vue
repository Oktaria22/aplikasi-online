<template>
  <div class="landing">
    <HeaderStore />
    <BannerStore />
    <category-store />
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderStore from '@/components/HeaderStore.vue'
import BannerStore from '@/components/BannerStore.vue'
import CategoryStore from '@/components/CategoryStore.vue'



export default {
  name: 'landingpage',
  components: {
    HeaderStore,
    BannerStore,
    CategoryStore
  }
}
</script>
