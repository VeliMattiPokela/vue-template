<template>
  <div id="app">
    <topNav></topNav>
    <div id="container">
        <router-view></router-view>
    </div>
  </div>
</template>

<script>
    import topNav from './components/TopNav'
    export default {
      name: 'app',
        components: {
            topNav
        }
    }
</script>

<style lang="sass">
    @import 'main.sass';


</style>
