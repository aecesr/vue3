<template>
<div id="app">
  <comment-app></comment-app>
</div>
</template>

<script>
import CommentApp from './components/CommentApp.vue';
export default {
  name: 'App',
  components: {
    CommentApp,
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }
   body{
          background-image: url("../img/img.jpg");
          background-repeat:no-repeat;
          background-size:100% 9999px;
        
      }
</style>
