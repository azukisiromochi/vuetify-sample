<template>
  <v-layout column justify-center align-center>
    <v-container md>
      <v-row class="mb-2" no-gutters>
        <v-col>
          <v-card class="pa-2 table-title-bar rounded-t-lg" outlined tile>
            Title
          </v-card>
        </v-col>
      </v-row>
      <v-row v-for="n in 2" :key="n" :class="n === 1 ? 'mb-1' : ''" no-gutters>
        <v-col v-for="k in 4" :key="k">
          <v-card
            class="pa-2"
            :class="k === 4 ? 'no-border' : ''"
            outlined
            tile
          >
            {{ k }} of {{ n + 1 }}
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-layout>
</template>

<script>
export default {}
</script>

<style lang="scss">
.theme--light.v-sheet--outlined {
  border: none;
  border-right: 2px solid;
  border-image: linear-gradient(
    #fff 0% 20%,
    $table-title-bar-color 20% 80%,
    #fff 80% 100%
  );
  border-image-slice: 1;
}
.table-title-bar.theme--light.v-sheet--outlined {
  @extend .no-border;
  // border: none;
}
.no-border {
  border: none !important;
}
</style>
