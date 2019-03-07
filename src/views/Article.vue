<template>
  <div class='article'>
    <div class="article-image" v-if="article.img" :style="{backgroundImage: bgImage}"></div>

    <div class='type' :class="typeClass" v-text='article.type'></div>
    <section>
      <h2 v-text='article.title'></h2>
      <p v-text='article.body'></p>
    </section>

    aha
  </div>
</template>

<script>
export default {
  name: 'Article',
  props: ['article'],

  computed: {
    bgImage() {
      return `url('${this.article.img}')`;
    },

    typeClass() {
      return this.article.type ? 'type-' + this.article.type.toLowerCase() : '';
    }
  }
}
</script>
