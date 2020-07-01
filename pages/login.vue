<template>
  <b-container fluid>
    <h1>Login</h1>
    <h2>With GitHub</h2>
    <form id="login-form" v-on:submit.prevent="submitForm">
      <b-row class="my-1">
        <b-col sm="3">
          <label for="username">User name:</label>
        </b-col>
        <b-col sm="9">
          <b-form-input
            id="username"
            type="text"
            v-model="userInfo.username"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="3">
          <label for="password">Password:</label>
        </b-col>
        <b-col sm="9">
          <b-form-input
            id="text"
            type="password"
            v-model="userInfo.password"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="3"> </b-col>
        <b-col sm="9">
          <b-button type="submit">Login</b-button>
        </b-col>
      </b-row>
    </form>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      errors: [],
      userInfo: {
        username: "",
        password: ""
      }
    };
  },
  methods: {
    valid: function() {
      if (this.userInfo.username && this.userInfo.password) return true;
      this.errors = [];
      if (!this.userInfo.username) this.errors.push("User name required.");
      if (!this.userInfo.password) this.errors.push("Password required.");
    },
    submitForm: function() {
      debugger;

      alert(JSON.stringify(this.userInfo, null, 2));
      if (this.valid()) {
        debugger;
        this.$auth.loginWith("github", { data: this.userInfo });
      }

      //TODO what to do with user data?
    }
  }
};
</script>

<style>
</style>
