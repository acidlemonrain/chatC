<template>
  <div style="margin-bottom:1rem">
    <v-card flat style="border:1px solid #ccc">
      <v-layout>
        <v-flex md1 class="hidden-sm-and-down">
          <div></div>
          <v-img
            src="https://images.unsplash.com/photo-1501004318641-b39e6451bec6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=600&q=60"
            class="img"
          ></v-img>
        </v-flex>

        <v-flex xs12 md10>
          <v-container>
            <v-layout>
              <span class="headline">HYC</span>
            </v-layout>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Facere nobis sunt saepe ea repellendus, reprehenderit dolorem, omnis deserunt illo labore quaerat quis!
            <v-card-actions>
              <v-spacer></v-spacer>date:2020-20-20
            </v-card-actions>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn small outline>more</v-btn>
            </v-card-actions>
          </v-container>
        </v-flex>
      </v-layout>
    </v-card>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.img {
  border-radius: 100%;
  transform: translate(-40%, 30%);
  border: 1px solid #ccc;
  display: inline-block;
  height: 70px;
  width: 70px;
}
</style>
