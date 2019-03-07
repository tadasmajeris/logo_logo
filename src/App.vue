<template>
  <transition
    appear mode="out-in"
    appear-class="invisible"
    appear-to-class="animated fadeIn"
    enter-active-class="animated fadeIn"
    leave-active-class="animated fadeOut">

    <main>
      <transition name="fade">
        <router-view :articles='articles'></router-view>
      </transition>
    </main>

  </transition>
</template>

<script>
export default {
  data() {
    return {
      articles: [],
    }
  },

  created() {
    this.$http.get("http://jsonplaceholder.typicode.com/posts")
      .then(response => response.json(), error => console.log(error))
      .then(json => this.setupArticles(json), error => console.log(error));
  },

  methods: {
    setupArticles(json) {
      this.articles = json.slice(10, 13);
      const customData = [
        { img: '/img/7.jpg', type: 'Article' },
        { img: '/img/4.jpg', type: 'News' },
        { img: '/img/5.jpg', type: 'Podcast' },
      ];

      // add custom images & types to articles
      this.articles = this.articles.map((article,i) => Object.assign(article, customData[i]));

      // make article body longer
      this.articles.forEach(article=>article.body=article.body.repeat(5));
    }
  }
}
</script>

<style lang="less">
  @font-face {
    font-family: "Open Sans Regular";
    src: url("assets/fonts/OpenSans/OpenSans-Regular.ttf");
  }
  @font-face {
    font-family: "Karma Light";
    src: url("assets/fonts/Karma/Karma-Light.ttf");
  }
  @font-face {
    font-family: "Karma SemiBold";
    src: url("assets/fonts/Karma/Karma-SemiBold.ttf");
  }

  * {
    font-family: 'Open Sans Regular', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
  #nav {
    padding: 30px;
    a {
      font-weight: bold;
      color: #2c3e50;
      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }

  /* transitions */
  .fade-enter-active, .fade-leave-active {
    transition-property: opacity;
    transition-duration: .25s;
  }

  .fade-enter-active {
    transition-delay: .25s;
  }

  .fade-enter, .fade-leave-active {
    opacity: 0
  }

  .fadePhoto-enter-active, .fadePhoto-leave-active {
    transition-property: opacity;
    transition-duration: .2s;
  }

  .fadePhoto-enter, .fadePhoto-leave-active {
    opacity: 0
  }
</style>
