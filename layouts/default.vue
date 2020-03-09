<template>
  <div>
    <AppHeader />
  <main>
    <b-container>
      <nuxt />
    </b-container>
  </main>
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue';

export default {
  components: {AppHeader}
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Muli&display=swap');

html {
  font-family: 'Muli', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

main {
  margin-left: 160px;
}
</style>
