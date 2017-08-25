<template>
  <div class="user__info">
    {{ location }}
  </div>
</template>

<script>
  export default {
    async asyncData () {
      const asyncData = {};

      await new Promise((resolve, reject) => {
        setTimeout(() => {
          asyncData.city = {
            name: 'New York',
            peoples: 40000000
          };
          resolve();
        }, 500)
      });

      return asyncData;
    },
    computed: {
      location () {
        return `User location: ${this.city.name}`;
      }
    }
  }
</script>
