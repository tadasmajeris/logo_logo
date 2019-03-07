<template>
  <div class="grid grid--gut12">

    <div v-for="article in articles" class="col col--12 col--4-ml col--6-mm article">

      <a :href="`/article/${article.id}`" v-text='article.title'></a>

      <img v-if="article.img" :src="article.img" />

    </div>

</div>

</template>

<script>
export default {
  name: 'HomeArticles',
  props: ['articles']
}
</script>
