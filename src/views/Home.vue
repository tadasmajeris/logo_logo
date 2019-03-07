<template>
  <div class="home home_pd">

    <header class="home_mg">
      <img alt="logo" src="../assets/img/logo/devtest_logo.png" />
      <div class='home_pd header-text'>
        <h1>Welcome to the test of your life</h1>
        <h2>This is a lead, it can go over two lines like so: Lorem ipsum dolor sit amet, consectetur.</h2>
      </div>
    </header>

    <HomeArticles :articles='articles'/>

    <OfficeMap />

    <section class="home_mg signup">
      <h1 class="h1_home">Sign up</h1>
      <p v-text="`Insert your details below and we'll get in touch.`"></p>
      <div class='home_pd signup-grid grid grid--gut12'>
        <div class='col col--12 col--6-ml py12 px12'>
          <label>First Name</label>
          <input class='input' />
        </div>
        <div class='col col--12 col--6-ml py12 px12'>
          <label>Surname</label>
          <input class='input' />
        </div>
        <div class='col col--12 col--6-ml py12 px12'>
          <label>Email</label>
          <input class='input' placeholder='eg. hello@email.co.uk'/>
        </div>
        <div class='col col--12 col--6-ml py12 px12'>
          <label>Company</label>
          <input class='input' />
        </div>
        <div class='button'>Submit</div>
      </div>
    </section>

    <footer class="home_mg">
      <section class='home_pd'>
        <img alt="logo" src="../assets/img/logo/devtest_logo-white.png" />
        <hr/>
        <ul class='fl'>
          <li>&copy; 2019 DEV TEST</li>
          <li>Terms & Conditions</li>
          <li>Accessibility</li>
          <li>Sitemap</li>
        </ul>
        <ul class='fr'>
          <li><img alt="twitter icon" src="../assets/img/icons/twitter.svg" /></li>
          <li><img alt="google-plus icon" src="../assets/img/icons/google-plus.svg" /></li>
          <li><img alt="linkedin icon" src="../assets/img/icons/linked-in.svg" /></li>
        </ul>
      </section>
    </footer>

  </div>
</template>

<script>
// @ is an alias to /src
import HomeArticles from '@/components/HomeArticles.vue';
import OfficeMap from '@/components/OfficeMap.vue';

export default {
  name: 'home',
  props: ['articles'],
  components: {
    HomeArticles, OfficeMap
  }
}
</script>

<style lang='less' scoped>
  @mobile:   ~"only screen and (max-width: 640px)";

  .home {
    text-align: center;

    header {
      margin: -1em -9em;
      margin-bottom: 0;
      padding-bottom: 11.4em;
      background-image: url('/img/3.jpg');
      background-size: cover;
      background-position: center;

      .header-text {
        max-width: 900px;
        padding: 1em 9em;
      }

      img {
        margin-top: 1.5em;
        margin-bottom: 10em;
        max-height: 80px;
      }

      h1 {
        font-family: 'Karma SemiBold';
        font-size: 4.5em;
        margin-bottom: 0.3em;
        color: #521C81;
        line-height: 1.2;
      }

      h2 {
        font-size: 1.5em;
      }

      h1, h2 {
        text-align: left;
      }
    }

    .signup {
      background-image: url('/img/6.jpg');
      background-size: cover;
      background-position-x: center;
      background-position-y: 75%;
      padding: 2em;

      .signup-grid {
        max-width: 960px;
        margin: auto;
        margin-top: 1em;
      }

      h1 {
        margin-bottom: 0.8em;
      }
      label {
        float: left;
        font-weight: bold;
        font-size: 14px;
        padding-bottom: 3px;
      }
      input {
        background-color: white;
        padding: 10px;
        &:focus {
          box-shadow: 0 0 1px orange;
        }
      }
      .button {
        margin: 2em auto 5em auto;
        cursor: pointer;
        background-color: #994adf;
        border-radius: 5px;
        padding: 0.7em 3em;
        padding-bottom: 0.8em;
        font-size: 14px;
        color: white;

        &:hover {
          box-shadow: 0px 3px 7px rgba(0, 0, 0, 0.4);
        }
      }
    }

    footer {
      padding-top: 3.3em;
      padding-bottom: 5.4em;
      text-align: left;
      background-color: #2c2828;
      hr {
        border-bottom: 2px solid #888;
        margin: 1.6em 0 2em 0;
      }
      ul li {
        color: #bbb;
        font-size: 14px;
        display: inline-block;
        padding-right: 2em;
        cursor: pointer;
        &:hover {
          color: white;
        }
        &:last-of-type {
          padding-right: 0;
        }

        img {
          -webkit-transition: none;
          -moz-transition: none;
          -o-transition: none;
          transition: none;

          &:hover {
            -webkit-filter: brightness(5);
            filter: brightness(5);
          }
        }
      }
    }

    @media @mobile {
      header {
        padding-bottom: 3em;

        h1 {
          font-size: 3.5em;
        }
      }

      footer {
        text-align: center;
        padding-bottom: 0;
        img {
          padding-bottom: 2em;
        }
        ul {
          padding-bottom: 1em;
          float: none !important;
        }
      }
    }
  }
</style>
