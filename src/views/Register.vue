<template>
  <div class="container p-3 my-3 bg-dark text-white" id="form">
    <h1> Register </h1>
    <form @submit.prevent="register">
        <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" class="form-control" id="email" placeholder="Enter email" name="email" v-model="email">
        </div>
        <div class="form-group">
        <label for="pwd">Password:</label>
        <input type="password" class="form-control" id="pwd" placeholder="Enter password" name="pswd" v-model="password">
        </div>
        <button type="submit" class="btn btn-primary">Register</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Register',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    register () {
      const payload = {
        email: this.email,
        password: this.password
      }
      this.$store.dispatch('register', payload)
        .then(({ data }) => {
          this.$router.push('/login')
        })
        .catch(({ err }) => {
          console.log(err)
        })
    }
  },
  created () {
    if (localStorage.access_token) {
      this.$router.push('/home')
    }
  }
}
</script>

<style>

</style>
