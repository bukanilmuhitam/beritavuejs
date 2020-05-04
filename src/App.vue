<template>
  <div id="app">
    <navBar />
    <contentNews />
    <footerBawah />
  </div>
</template>

<script>
import navBar from './components/navBar.vue';
import contentNews from './components/contentNews.vue';
import footerBawah from './components/footerBawah.vue';

export default {
  name: 'App',
  components: {
    navBar,
    contentNews,
    footerBawah,
  },
}
</script>
