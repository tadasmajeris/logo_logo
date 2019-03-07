<template>

  <div class="col col--12 col--4-mxl col--6-ml py12 px12">
    <div class='article'>
      <div class="article-image" v-if="img" :style="{backgroundImage: bgImage}"></div>
      <div class='type' :class="typeClass" v-text='type'></div>
      <section>
        <h2 v-text='title'></h2>
        <p v-text='shortBody'></p>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeArticleItem',
  props: ['title', 'img', 'id', 'type', 'body'],

  computed: {
    bgImage() {
      return `url('${this.img}')`;
    },

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
    border: 1px solid #eee;
    border-radius: 5px;
    height: 100%;
    cursor: pointer;

    &:hover {
      box-shadow: 0px 30px 30px rgba(0, 0, 0, 0.1); ;
    }

    .article-image {
      height: 203px;
      background-size: cover;
      background-position: center;
      border-radius: inherit;
      border-bottom-left-radius: 0;
      border-bottom-right-radius: 0;
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

    section {
      padding: 1.5em 1em;

      h2 {
       font-family: 'Karma SemiBold';
       font-size: 23px;
      }

      p {
        font-size: 14px;
      }
    }
  }
</style>
