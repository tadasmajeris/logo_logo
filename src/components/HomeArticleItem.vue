<template>
  <div class="col col--12 col--4-ml col--6-mm article">
    <img v-if="img" :src="img" />
    <h2 v-text='title'></h2>
    <p v-text='shortBody'></p>
  </div>
</template>

<script>
export default {
  name: 'HomeArticleItem',
  props: ['title', 'img', 'id', 'type', 'body'],

  computed: {
    shortBody() {
      return this.body.slice(0, 100) + '...';
    }
  }
}
</script>

<style lang="less" scoped>
  .article {
    text-align: left;

    h2 {
     font-family: 'Karma SemiBold';
     font-size: 18px;
    }
  }
</style>
