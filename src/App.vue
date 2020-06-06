<template>
    <div id="app">
        <router-view />
        <div class="footer-comp"><Footer /></div>
    </div>
</template>

<script>
import Footer from '@/components/Footer.vue'
export default {
    name: 'App',
    components: {
        Footer,
    },
}
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap')
body
  padding: 0
  margin: 0
#app
  font-family: 'Patrick Hand', cursive
  width: 100%
  // height: 100%
  text-align: center
  .footer-comp
    width: 100%
    height: 30px
</style>
