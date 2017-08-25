<template>
  <div class="user__comments">

    <ul class="user__comments-list" v-if="comments && comments.length">
      <li v-for="comment in comments">
        {{ comment }}
      </li>
    </ul>

  </div>
</template>

<script>
  const comments = [
    'I like nuxt framework!',
    'But asyncData for children page not working',
    'Super! It`s fixed'
  ];

  export default {
    async asyncData () {
      const asyncData = {};

      await new Promise((resolve, reject) => {
        setTimeout(() => {
          asyncData.comments = comments;
          resolve();
        }, 500)
      });

      return asyncData;
    }
  }
</script>
<style>
  .user__comments-list {
    padding: 0;
    list-style-position: inside;
    list-style-type: decimal;
  }
  .user__comments-list li {
    padding: 8px 0;
    border-top: 1px solid #f5f5f5;
  }
</style>
