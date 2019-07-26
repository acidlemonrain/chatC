<template>
  <v-container>
    <v-layout align-start>
      <v-flex md3 class="leftBoard hidden-sm-and-down">
        <v-container>
          <leftcard v-for="n in 3" :key="n"></leftcard>
        </v-container>
      </v-flex>
      <v-flex md9 xs12 class="main">
        <v-layout column>
          <v-flex>
            <v-layout>
              <v-toolbar flat style="border:1px solid #ccc">
                <v-toolbar-title>Title</v-toolbar-title>

                <v-spacer></v-spacer>

                <v-toolbar-items>
                  <v-text-field></v-text-field>
                  <v-btn icon>
                    <v-icon>search</v-icon>
                  </v-btn>
                </v-toolbar-items>
              </v-toolbar>
            </v-layout>
          </v-flex>
          <v-flex>
            <v-container>
              <v-layout column>
                <zcard v-for="index in 8 " :key="index"></zcard>
              </v-layout>
            </v-container>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import zcard from "~/components/zoneCard.vue";
import leftcard from "~/components/leftCard.vue";
export default {
  components: {
    zcard,
    leftcard
  }
};
</script>

<style>
</style>
