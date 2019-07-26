<template>
  <v-layout style=" margin-bottom:1rem;border:1px solid #ccc">
    <v-list subheader three-line>
      <v-subheader>userhome</v-subheader>

      <v-list-tile v-for="n in 3" :key="n">
        <v-list-tile-content>
          <v-list-tile-title>Content filtering</v-list-tile-title>
          <v-list-tile-sub-title>hyc hyc Lorem ipsum dolor sit, amet consectetur adipisicing elit. Aspernatur maiores quod quasi.</v-list-tile-sub-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-layout>
</template>

<script>
export default {};
</script>

<style>
</style>
