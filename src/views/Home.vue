<template>
  <div class="home">
    <img alt="logo" src="../assets/img/logo/devtest_logo.png">
    <h1 class='txt-h1'>Welcome to the test of your life</h1>
    <p>This is a lead, it can go over two lines like so: Lorem ipsum dolor sit amet, consectetur.</p>

    <HomeArticles :articles='articles'/>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeArticles from '@/components/HomeArticles.vue'

export default {
  name: 'home',
  props: ['articles'],
  components: {
    HomeArticles
  }
}
</script>

<style lang='less' scoped>
  .home {
    padding: 1em;
    text-align: center;

    h1 {
      font-family: 'Karma SemiBold';
      color: #521C81;
    }
  }
</style>
