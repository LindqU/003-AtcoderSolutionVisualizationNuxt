<script lang = 'ts'>
export default {
  data: () => ({
    cards: [
      {
        title: "A - Contest Result",
        flex: 6,
        href: "abc290/a",
      },
      {
        title: "B - Qual B",
        flex: 6,
        href: "",
      },
      {
        title: "C - Max MEX",
        flex: 6,
        href: "",
      },
      {
        title: "D - Marking",
        flex: 6,
        href: "",
      },
    ],
  }),
};
</script>
<template>
  <v-container fluid>
    <v-row dense>
      <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
        <v-card :to="card.href">
          <v-img
            class="align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="200px"
            cover
          >
            <v-card-title class="text-white">{{ card.title }}</v-card-title>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>