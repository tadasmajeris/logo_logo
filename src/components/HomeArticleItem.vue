<template>
  <div class="col col--12 col--4-ml col--6-mm article">
    <img v-if="img" :src="img" />
    <div class='type' :class="typeClass" v-text='type'></div>
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
    },

    typeClass() {
      return 'type-' + this.type.toLowerCase();
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

    .type {
      color: white;
      width: fit-content;
      position: absolute;
      margin-top: -25px;
      margin-left: 6px;
      font-size: 12px;
      font-weight: bold;
      padding: 0 7px;
      border-radius: 5px;
      line-height: 1.6;
    }
    .type-news {
      background-color: #994adf;
    }
    .type-article {
      background-color: #f1c00a;
    }
    .type-podcast {
      background-color: #0e63e7;
    }
  }
</style>
