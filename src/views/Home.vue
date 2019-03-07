<template>
  <div class="home">
    <img alt="logo" src="../assets/img/logo/devtest_logo.png">
    <p>Hello from home</p>

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
