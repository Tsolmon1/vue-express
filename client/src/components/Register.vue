<template>
  <div>
    <h1>Register</h1>
    <input type="email" name="email" placeholder="email" v-model="email" />
    <br>
    <input type="password" name="password" placeholder="password" v-model="password" />
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data() {
    return { 
      email: "abc", 
      password: "123" 
      }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data);
      // console.log('register button was clicked!', this.email, this.password)
    }
  }
/*   watch: {
    email (value) {
      console.log('email has changed', value)
    }
  }, */
/*   mounted () {
    setTimeout(() => {
      this.email = 'hello world'
    }, 1000)
  } */
}
</script>

<style scoped></style>
