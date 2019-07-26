<template>
  <div>
    <v-container>
      <v-layout wrap>
        <v-flex xs12>
          <v-card flat class="blue lighten-5" width="100%">
            <v-img src="https://cdn.vuetifyjs.com/images/cards/desert.jpg" aspect-ratio="2.75"></v-img>
            <div class="pa-5">
              <div class="display-1">welcome to chatting chatting</div>

              <v-layout wrap>
                <v-spacer></v-spacer>
                <div class="hidden-sm-and-up">
                  <v-layout column align-start>
                    <v-btn small width="100%" :to="'/chat'">anyonmous</v-btn>
                    <v-btn small width="100%" :to="'/inspire'">i am a user</v-btn>
                  </v-layout>
                </div>
                <div class="hidden-sm-and-down">
                  <v-btn outline right="true" :to="'/chat'">anyonmous</v-btn>
                  <v-btn outline right="true" :to="'/inspire'">i am a user</v-btn>
                </div>
              </v-layout>
            </div>
          </v-card>
        </v-flex>
      </v-layout>
      <div class="container">
        <h1>Home page</h1>
        <p>
          <NuxtLink to="/about">About page</NuxtLink>
        </p>
        <p>
          <NuxtLink to="/users">Lists of users</NuxtLink>
        </p>
      </div>
      <br />
      <show></show>
    </v-container>
  </div>
</template>

<script>
import show from "~/components/show.vue";

export default {
  components: {
    show
  },
  data: () => {
    return {
      com: false
    };
  },
  mounted() {
    setTimeout(() => {
      this.com = !this.com;
    }, 700);
  }
};
</script>

<style>
.tweakOpacity-enter-active,
.tweakOpacity-leave-active {
  transition: opacity 2s ease-out;
}
.tweakOpacity-enter,
.tweakOpacity-leave-active {
  opacity: 0;
}
</style>
