<template>
  <v-card flat class="pa-3" outline width="100%">
    <v-container>
      <v-layout>
        <h1>Login</h1>
      </v-layout>
    </v-container>
    <v-text-field v-model="username" label="username" outline placeholder="Placeholder"></v-text-field>

    <v-text-field v-model="password" label="password" outline placeholder="Placeholder"></v-text-field>
    <div>
      <v-layout>
        <v-btn block outline small @click="login">confirm</v-btn>
      </v-layout>
    </div>
  </v-card>
</template>

<script>
export default {
  methods: {
    login() {
      this.$router.push("/home");
    }
  }
};
</script>

<style>
</style>
