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
      :loading="isLoading"
    ></v-data-table>
  </v-card>
</template>

<script>
  import axios from 'axios'

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
        players: [],
        isLoading: false,
      }
    },
    methods: {
      getData: function() {
        var that = this;

        this.isLoading = true;

        axios.get('https://minecraft-api.serbaonline.id/minecraft/getPlayersData')
        .then(function (response) {
          that.players = [];

          if (response.data != false) {
            var noNow = 1;
            response.data.forEach(function(item, index, arr) {
              that.players.push({no: noNow, nama: item});
              
              noNow++;
            })
          }

          that.isLoading = false;
        })
        .catch(function () {
          console.log('Error happened...');
        });
      }
    },
    mounted: function() {
      setInterval(this.getData, 5000);
    }
  }
</script>