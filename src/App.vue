<template>
  <transition
    appear mode="out-in"
    appear-class="invisible"
    appear-to-class="animated fadeIn"
    enter-active-class="animated fadeIn"
    leave-active-class="animated fadeOut">

    <main>
      <transition name="fade">
        <router-view :articles='articles' :article="selectedArticle"></router-view>
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

  computed: {
    selectedArticle() {
      const id = this.$route.params.id;
      return this.articles.find(article=>id==article.id);
    }
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
    color: #4A4A4A;
  }

  h1, h2, h3, h4, h5, h6 {
    color: #2c2828;
  }

  .h1_home {
    font-family: 'Karma Light';
    font-size: 2.6em;
    margin: 1.5em;
  }

  @desktop:   ~"only screen and (min-width: 960px)";
  @mobile:   ~"only screen and (max-width: 640px)";
  @tablet:    ~"only screen and (min-width: 720px) and (max-width: 959px)";

  @media @mobile {
    .home_pd {
      padding: 1em !important;
    }
    .home_mg {
      margin: -1em !important;
    }

    .grid {
      margin-right: -12px;
    }
  }

  @media @tablet {
    .home_pd {
      padding: 3em !important;
    }
    .home_mg {
      margin: -3em !important;
    }
  }

  @media @desktop {
    .home_pd {
      padding: 1em 9em !important;
    }
    .home_mg {
      margin: -1em -9em !important;
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

  *, *:after {
    -webkit-transition: 0.2s ease-out;
    -moz-transition: 0.2s ease-out;
    -o-transition: 0.2s ease-out;
    transition: 0.2s ease-out;
  }
</style>
