<template>
  <!-- <div>
    <h2>Login</h2>
  </div> -->
  <v-container>
    <v-layout row wrap>
      <v-flex xs12>
        <h2>Login</h2>
      </v-flex>
      <v-spacer></v-spacer>
      <v-flex xs12 sm6 offset-sm3>
        <v-text-field
        label="Email"
        v-model="email"
        v-bind:rules="emailRules"
        required>
        </v-text-field>
      </v-flex>
      <v-flex xs12 sm6 offset-sm3>
        <v-text-field
        label="Password"
        v-model="password"
        v-bind:rules="passwordRules"
        v-bind:type="'password'"
        required>
        </v-text-field>
      </v-flex>
      <v-flex xs12 sm6 offset-sm3>
        <v-btn v-on:click="cancel">Cancel</v-btn>
        <v-btn color="primary" v-on:click="login">Login</v-btn>
      </v-flex>
    </v-layout>
    <v-snackbar
      :timeout="6000"
      :top="true"
      v-model="showAlert">
      {{message}}
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      emailRules: [
        v => !!v || 'Email is required',
        v => /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(v) || 'Email must be valid'
      ],
      password: '',
      passwordRules: [
        v => !!v || 'Password is required'
      ],
      showAlert: false,
      message: ''
    }
  },
  methods: {
    login: function () {
      const vm = this
      if (vm.password === 'password-1') {
        this.$router.push({ path: '/' })
      } else {
        vm.showAlert = true
        vm.message = 'Email or password is invalid'
      }
    },
    cancel: function () {
      console.log('User cancelled')
      this.showAlert = false
    }
  }
}
</script>

<style>

</style>
