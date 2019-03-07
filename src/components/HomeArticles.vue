<template>
  <div class='articles-pages'>
    <h1>Articles Pages</h1>

    <section class="grid grid--gut12">
      <HomeArticleItem v-for="{id, type, body, img} in articles"
        :key='id' :type="type" :body="body" :img="img" :id="id" />
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
