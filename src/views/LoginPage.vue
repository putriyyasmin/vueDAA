<template>
    <h1> Login </h1>
    <v-sheet class="mx-auto" width="300">
      <v-form fast-fail @submit.prevent>
        <v-text-field
          v-model="userName"
          :rules="userNameRules"
          label="Username"
        ></v-text-field>
  
        <v-text-field
          v-model="password"
          :rules="passwordRules"
          
          label="Password"
        ></v-text-field>
  
        <v-btn class="mt-2" type="submit" block>Submit</v-btn>
      </v-form>
    </v-sheet>
  </template>
  <script>
    export default {
      data: () => ({
        userName: '',
        userNameRules: [
          value => {
            if (value?.length >= 3) return true
  
            return 'Username must be at least 3 characters.'
          },
        ],
        password: '123',
        passwordRules: [
          value => {
            if (/[^0-9]/.test(value)) return true
  
            return 'Password can not contain digits.'
          },
        ],
      }),
    }
  </script>