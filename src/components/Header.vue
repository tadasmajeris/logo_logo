<template>
  <header class="home_mg">
    <img alt="logo" src="../assets/img/logo/devtest_logo.png" />
    <div class='home_pd header-text'>
      <h1>Welcome to the test of your life</h1>
      <h2>This is a lead, it can go over two lines like so: Lorem ipsum dolor sit amet, consectetur.</h2>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang='less' scoped>
  @mobile:   ~"only screen and (max-width: 640px)";

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

    @media @mobile {
      padding-bottom: 3em;

      h1 {
        font-size: 3.5em;
      }
    }
  }
</style>
