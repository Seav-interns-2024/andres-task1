<template>
  <nav class="navbar navbar-expand navbar-light fixed-top">
    <div class="container">
      <a href="#" class="navbar-brand" @click.prevent="navigateToHome">Say Hi !</a>
      <div class="">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a href="#" class="nav-link" @click.prevent="goToLogin">Login</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link" @click.prevent="goToSignup">Sign up</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Nav',
  methods: {
    goToLogin() {
      this.$emit('navigate', 'login');
    },
    goToSignup() {
      this.$emit('navigate', 'Signup');
    },
    navigateToHome() {
      this.$emit('navigate', 'Home');
    }
  }
};
</script>
