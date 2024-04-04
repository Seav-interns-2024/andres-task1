<template>
    <form @submit.prevent="handleSubmit">
  
      <h3>Sign Up</h3>
  
      <div class="form-group d-inline-block">
        <label>First Name</label>
        <input type="text" class="form-control" placeholder="First Name" v-model="firstName">
      </div>
  
      <div class="form-group d-inline-block">
        <label>Middle Name</label>
        <input type="text" class="form-control" placeholder="Middle Name" v-model="middleName">
      </div>
  
      <div class="form-group d-inline-block">
        <label>Last Name</label>
        <input type="text" class="form-control" placeholder="Last Name" v-model="lastName">
      </div>
  
      <div class="form-group d-inline-block">
        <label>Suffix</label>
        <select class="form-control" v-model="suffix" required>
          <option value="">Select Suffix</option>
          <option value="mr">Mr.</option>
          <option value="ms">Ms.</option>
          <option value="mrs">Mrs.</option>
          <option value="dr">Dr.</option>
        </select>
      </div>
  
      <div class="form-group d-inline-block">
        <label>Contact Number</label>
        <input type="tel" class="form-control" placeholder="Contact Number" v-model="contactNumber">
      </div>
  
      <div class="form-group d-inline-block">
        <label>Date of Birth</label>
        <input type="date" class="form-control" placeholder="Date of Birth" required v-model="dateOfBirth">
      </div>
  
      <div class="form-group d-inline-block">
        <label>Age</label>
        <input type="number" class="form-control" placeholder="Age" v-model="age">
      </div>
  
      <div class="form-group d-inline-block">
        <label>Gender</label>
        <select class="form-control" required v-model="gender">
          <option value="">Select Gender</option>
          <option value="male">Male</option>
          <option value="female">Female</option>
          <option value="other">Other</option>
        </select>
      </div>
  
      <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>Email</label>
            <input type="email" class="form-control" placeholder="Email" v-model="email">
          </div>
          <div class="form-group">
            <label>Data Privacy Consent</label>
            <div>
              <input type="checkbox" id="consentCheckbox" v-model="consent" required>
              <label for="consentCheckbox">I consent to data processing.</label>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <div class="form-group">
            <label>Password</label>
            <input type="password" class="form-control" placeholder="Password" v-model="password">
          </div>
          <div class="form-group">
            <label>Confirm Password</label>
            <input type="password" class="form-control" placeholder="Confirm Password" v-model="confirmPassword">
          </div>
        </div>
      </div>
  
      <div class="text-center">
        <button class="btn btn-primary w-100">Sign up</button>
      </div>
  
      <!-- Display entered data -->
      <div v-if="displayData">
        <h4>Entered Data:</h4>
        <p>First Name: {{ firstName }}</p>
        <p>Middle Name: {{ middleName }}</p>
        <p>Last Name: {{ lastName }}</p>
        <p>Suffix: {{ suffix }}</p>
        <p>Contact Number: {{ contactNumber }}</p>
        <p>Date of Birth: {{ dateOfBirth }}</p>
        <p>Age: {{ age }}</p>
        <p>Gender: {{ gender }}</p>
        <p>Email: {{ email }}</p>
        <p>Data Privacy Consent: {{ consent ? 'Yes' : 'No' }}</p>
        <p>Password: {{ password }}</p>
        <p>Confirm Password: {{ confirmPassword }}</p>
      </div>
  
    </form>
  </template>
  
  <script>
  export default {
    name: 'Signup',
    data() {
      return {
        firstName: '',
        middleName: '',
        lastName: '',
        suffix: '',
        contactNumber: '',
        dateOfBirth: '',
        age: '',
        gender: '',
        email: '',
        consent: false,
        password: '',
        confirmPassword: ''
      };
    },
    computed: {
      displayData() {
        return this.firstName || this.middleName || this.lastName || this.suffix || this.contactNumber ||
          this.dateOfBirth || this.age || this.gender || this.email || this.password || this.confirmPassword || this.consent;
      }
    },
    methods: {
      handleSubmit() {
        this.$emit('navigate', 'Home');
      }
    }
  }
  </script>

<style>
.form-group{
  margin: 15px 5px;
}
</style>