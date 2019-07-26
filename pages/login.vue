<template>
  <v-container>
    <v-layout justify-center wrap>
      <v-flex xs12 md9>
        <v-layout wrap justify-center style="border:2px solid #ccc; ">
          <v-flex md8>
            <v-img
              src="https://images.unsplash.com/photo-1499744632587-7798360ba20f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=600&q=60"
              alt
              height="100%"
            ></v-img>
          </v-flex>
          <v-flex xs12 md4>
            <login></login>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import login from "~/components/login.vue";
export default {
  components: {
    login
  }
};
</script>

<style>
</style>
