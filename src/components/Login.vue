<template>
  <form @submit.prevent="handleSubmit">
    <h3>Login</h3>

    <div class="form-group">
      <label for="email">Email</label>
      <input type="email" id="email" class="form-control" placeholder="Email" v-model="email" required>
    </div>

    <div class="form-group">
      <label for="password">Password</label>
      <input type="password" id="password" class="form-control" placeholder="Password" v-model="password" required>
    </div>

    <div class="row">
      <div class="col-md-6">
        <p> Don't have an account yet?</p>
      </div>
      <div class="col-md-6 ta-r">
        <a href="#" class="nav-link" @click.prevent="goToSignup">Sign up</a>
      </div>
    </div>

    <button type="submit" class="btn btn-primary btn-block">Login</button>
    <div v-if="email || password" class="mt-3">
      <p>Email: {{ email }}</p>
      <p>Password: {{ password }}</p>
    </div>
  </form>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    goToSignup() {
      this.$emit('navigate', 'Signup');
    },
    handleSubmit() {
      this.$emit('navigate', 'Home');
    }
  }
}
</script>

<style scoped>
  .form-group{
    margin: 30px 5px;
  }
  .ta-r{
    text-align: right;
  }
</style>
