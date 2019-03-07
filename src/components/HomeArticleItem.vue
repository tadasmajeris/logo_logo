<template>
  <div class="col col--12 col--4-ml col--6-mm article">
    <img v-if="img" :src="img" />
    <h2 v-text='title'></h2>
    <p v-text='body'></p>
  </div>
</template>

<script>
export default {
  name: 'HomeArticleItem',
  props: ['title', 'img', 'id', 'type', 'body']
}
</script>
