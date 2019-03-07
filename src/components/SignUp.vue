<template>
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
</template>

<script>
export default {
  name: 'SignUp',
}
</script>

<style lang='less' scoped>
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
</style>
