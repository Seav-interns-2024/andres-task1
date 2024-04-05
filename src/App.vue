<template>
  <div id="app">
    <Nav @navigate="handleNavigation" />
    <div class="main-container">
      <div class="image-container">
        <img src="./assets/rule-the-killer-v0-fleat0flaaaa1.jpg" alt="TaskLogo" class="image">
      </div>
      <div class="wrapper-container">
        <div class="auth-wrapper">
          <div class="auth-inner">
            <div v-if="currentRoute === 'login'">
              <Login @navigate="handleNavigation" />
            </div>
            <div v-else-if="currentRoute === 'Signup'">
              <Signup @navigate="handleNavigation" />
            </div>
            <div v-else-if="currentRoute === 'Home'">
              <Home @navigate="handleNavigation" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Nav from './components/Nav.vue'
import Login from './components/Login.vue'
import Signup from './components/Signup.vue'
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Login,
    Signup,
    Home,
  },
  data() {
    return {
      currentRoute: 'login'
    }
  },
  methods: {
    handleNavigation(route) {
      console.log("counter2")
      this.currentRoute = route;
    }
  }
}
</script>



<style scoped>
@import url('https://fonts.googleapis.com/css?family=Fira+Sans:400,500,600,700,800');

* {
  box-sizing: border-box;
}


.main-container {
  display: flex;
  flex-direction: row;
  background: #ee8e936c;
}

.image-container {
  width: 50%;
}

.wrapper-container {
  width: 50%;
}


body {
  background: #ee8e936c;
  min-height: 100vh;
  display: flex;
  font-weight: 400;
  font-family: 'Fira Sans', sans-serif;
}

h1,
h2,
h3,
h4,
h5,
h6,
label,
span {
  font-weight: 500;
  font-family: 'Fira Sans', sans-serif;
}

body,
html,
#app,
#root,
.auth-wrapper {
  width: 100%;
  height: 100%;
}

#app {
  text-align: center;
}


.navbar-light {
  background-color: #ffffff;
  box-shadow: 0px 14px 80px rgba(34, 35, 58, 0.2);
}

.image {
  border-radius: 10px;
}

.auth-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: left;
  height: 100vh;
  max-width: 80%;
  margin: auto;
}

.auth-inner {
  width: 800px;
  margin: auto;
  background: #ffffff;
  box-shadow: 0px 14px 80px rgba(34, 35, 58, 0.2);
  padding: 40px 55px 45px 55px;
  border-radius: 15px;
  transition: all .3s;
}

.auth-wrapper .form-control:focus {
  border-color: #167bff;
  box-shadow: none;
}

.auth-wrapper h3 {
  text-align: center;
  margin: 0;
  line-height: 1;
  padding-bottom: 20px;
  padding-top: 50px;
}

.custom-control-label {
  font-weight: 400;
}

.forgot-password,
.forgot-password a {
  text-align: right;
  font-size: 13px;
  padding-top: 10px;
  color: #7f7d7d;
  margin: 0;
}

@media screen and (max-width: 1368px) {
  .main-container {
    flex-direction: column;
  }

  .image-container,
  .wrapper-container {
    width: 100%;
    height: 100%;
    margin: 0;
    display: flex;
    background-attachment: fixed;
  }


}

.image-container {
  display: flex;
  justify-content: center;
  /* Horizontally center the image */
  align-items: center;
  /* Vertically center the image */
  max-width: 80%;
  /* Make the image flexible within its container */
  height: auto;
  /* Maintain the aspect ratio */
  height: 100vh;
  max-width: 100%;
}
</style>
