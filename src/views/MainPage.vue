<template>
<div>
  <navbar />
  <router-view />
</div>

</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
  name: 'MainPage'
}
</script>

<style>

</style>
