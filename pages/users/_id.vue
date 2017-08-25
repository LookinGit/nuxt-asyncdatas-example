<template>
  <section class="container">

    <div class="user__home-link">
      <nuxt-link class="button" to="/">
        Home page
      </nuxt-link>
    </div>

    <h1 class="title">
      {{ username }}
    </h1>

    <ul class="user__menu">
      <li>
        <nuxt-link to="/users/1" exact>
          User info
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/users/1/comments" exact>
          User comments
        </nuxt-link>
      </li>
    </ul>

    <div class="user__more">
      <nuxt-child></nuxt-child>
    </div>
  </section>
</template>

<script>
  export default {
    async asyncData () {
      const asyncData = {};

      await new Promise((resolve, reject) => {
        setTimeout(() => {
          asyncData.username = 'John Smith';
          resolve();
        }, 2000)
      });

      return asyncData;
    }
  }
</script>
<style>
  .user__menu {
    display: flex;
    list-style: none;
    justify-content: center;
    padding: 0;
  }
  .user__menu li {
    margin: 0 12px;
  }
  .user__menu .nuxt-link-active {
    text-decoration: none;
    color: #000;
  }
  .user__home-link {
    margin-bottom: 24px;
  }
  .user__more {
    margin-top: 24px;
  }
</style>
