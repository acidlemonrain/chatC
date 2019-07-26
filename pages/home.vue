<template>
  <v-container>
    <v-layout justify-center wrap>
      <v-flex xs12 md8>
        <v-card width="100%" class="mt-5" flat style="border:1px solid #ccc">
          <img
            src="https://images.unsplash.com/photo-1499892477393-f675706cbe6e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=600&q=60"
            alt
            class="img"
            style="border:1px solid #ccc"
          />

          <v-container>
            <v-layout wrap justify-center>
              <v-flex md10>
                <v-container>
                  <v-layout>
                    <v-spacer></v-spacer>

                    <v-badge color="red">
                      <template v-slot:badge>
                        <span>36</span>
                      </template>
                      <v-icon large color="grey">mail</v-icon>
                    </v-badge>
                  </v-layout>

                  <v-divider></v-divider>

                  <homelist></homelist>
                </v-container>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import homelist from "~/components/homelist.vue";
export default {
  components: {
    homelist
  }
};
</script>

<style scoped>
.img {
  position: relative;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 100%;
  height: 100px;
  width: 100px;
}
</style>

