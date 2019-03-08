<template>
  <div class='home-articles'>
    <h1 class='h1_home' v-text='title'></h1>

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
  props: ['articles', 'title'],
  components: {
    HomeArticleItem
  },
}
</script>

<style lang='less' scoped>
  .home-articles {
    margin-bottom: 2em;

    h1 {
      margin-top: 3.6em;
    }
  }
</style>
