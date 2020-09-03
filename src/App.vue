<template>
  <div class="app-container">
    <Header class="header"/>
    <Navigation class="navigation"/>
    <Main class="main"/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Navigation from '@/components/Navigation.vue';
import Main from '@/components/Main.vue';

export default {
  name: 'App',

  components: {
    Header, Navigation, Main,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');
@import url('./assets/normalize.scss');
.app-container{
  width: 100%;
  display: grid;
  grid-template-columns: 190px auto;
  grid-template-rows: 55px auto;
  grid-template-areas:
  "navigation header"
  "navigation main";
}
.header{
  grid-area: header;
}
.navigation{
  grid-area: navigation;
}
.main{
  grid-area: main;
}
</style>
