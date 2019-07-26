<template>
  <div>
    <div class="first">
      <v-layout wrap>
        <v-flex sm12 md6>
          <v-card flat class="show pa-5 purple lighten-5">
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Debitis consequatur veritatis voluptate.
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn outline>find more</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
        <v-flex sm12 md6 class="show pa-5 orange lighten-5">
          <div>this is us!</div>

          <v-spacer></v-spacer>
          <v-btn outline>learn more</v-btn>
        </v-flex>
      </v-layout>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {};
  }
};
</script>

<style>
.flex {
  display: flex;
}
</style>
