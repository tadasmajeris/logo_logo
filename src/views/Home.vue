<template>
  <div class="home home_pd">

    <Header />
    <HomeArticles :articles='articles' />
    <OfficeMap />
    <SignUp />
    <Footer />

  </div>
</template>

<script>
// @ is an alias to /src
import HomeArticles from '@/components/HomeArticles.vue';
import OfficeMap from '@/components/OfficeMap.vue';
import SignUp from '@/components/SignUp.vue';
import Footer from '@/components/Footer.vue';
import Header from '@/components/Header.vue';

export default {
  name: 'home',
  props: ['articles'],
  components: {
    HomeArticles, OfficeMap, SignUp, Footer, Header
  }
}
</script>

<style lang='less' scoped>
  .home {
    text-align: center;
  }
</style>
