<template>
  <v-card>
    <v-card-title>
      Minecraft Players
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      dense
      :headers="headers"
      :items="players"
      :search="search"
    ></v-data-table>
  </v-card>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data () {
      return {
        search: '',
        headers: [
          {
            text: 'No',
            align: 'start',
            sortable: false,
            value: 'no',
          },
          { text: 'Nama', value: 'nama' },
        ],
        players: [
          {
            no: 1,
            nama: 'AgungDH'
          },
        ],
      }
    },
  }
</script>