<template>
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
</template>

<script>
export default {
  name: 'Footer',
}
</script>

<style lang='less' scoped>
  @mobile:   ~"only screen and (max-width: 640px)";

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

    @media @mobile {
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
</style>
