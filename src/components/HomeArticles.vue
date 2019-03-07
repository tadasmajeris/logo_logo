<template>
  <div class='home-articles'>
    <h1>Articles Pages</h1>

    <section class="grid grid--gut12">
      <HomeArticleItem v-for="{id, type, title, body, img} in articles"
        :key='id' :type="type" :title="title"
        :body="body" :img="img" :id="id"
      />
    </section>

  </div>
</template>

<script>
import HomeArticleItem from './HomeArticleItem';

export default {
  name: 'HomeArticles',
  props: ['articles'],
  components: {
    HomeArticleItem
  }
}
</script>

<style lang='less' scoped>
  .home-articles {
    h1 {
      font-family: 'Karma Light';
      font-size: 2.6em;
      margin: 1.5em;
      margin-top: 3.6em;
    }
  }
</style>
