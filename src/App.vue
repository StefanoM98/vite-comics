<script>
import AppHeader from './components/AppHeader.vue';
import ContentSection from './components/ContentSection.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  components: {
    AppHeader,
    ContentSection,
    AppFooter
  }
}
</script>

<template>
  <AppHeader />
  <ContentSection />
  <AppFooter />
</template>

<style lang="scss">
@use "../src/style/general.scss"
</style>
