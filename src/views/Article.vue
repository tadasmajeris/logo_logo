<template>
  <div class="home home_pd">

    <Header isArticle='1'/>

    <div class='article'>
      <p>March 7 2019</p>
      <h1 v-if="article" class='txt-h1' v-text='article.title'></h1>

      <div class="article-image" v-if="article && article.img" :style="{backgroundImage: bgImage}"></div>

      <section>
        <p v-if='article' v-text='article.body'></p>
      </section>

    </div>

    <HomeArticles :articles='articles' title="Other Pages" />

    <SignUp />
    <Footer />

  </div>

</template>

<script>
import HomeArticles from '@/components/HomeArticles.vue';
import SignUp from '@/components/SignUp.vue';
import Footer from '@/components/Footer.vue';
import Header from '@/components/Header.vue';

export default {
  name: 'Article',
  props: ['articles', 'article'],
  components: {
    HomeArticles, SignUp, Footer, Header
  },

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

<style lang='less' scoped>
  @mobile:   ~"only screen and (max-width: 640px)";
  @tablet:    ~"only screen and (min-width: 640px) and (max-width: 959px)";

  .home {
    text-align: center;

    .article {
      text-align: left;
      padding: 1em;
      padding-top: 5em;

      h1 {
        color: #521c81;
        margin-bottom: 1.2em;
      }

      .article-image {
        height: 500px;
        margin: 2em 0;
        background-size: cover;
        background-position: center;

        @media @tablet {
          height: 400px;
        }

        @media @mobile {
          height: 300px;
        }
      }

    }
  }
</style>
