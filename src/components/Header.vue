<template>
  <v-card>
    <v-list-item>
      <v-list-item-content>
        <div class="overline mb-4">
          Current Time: {{time}}
        </div>
      </v-list-item-content>
    </v-list-item>
  </v-card>
</template>

<script>
  export default {
    name: 'Header',
    data () {
      return {
        time: '',
      }
    },
    methods: {
        setTime: function() {
            var date = new Date();
            this.time = `${date.getDate().toString().padStart(2, '0')}-${date.getMonth().toString().padStart(2, '0')}-${date.getFullYear().toString().padStart(2, '0')} ${date.getHours().toString().padStart(2, '0')}:${date.getMinutes().toString().padStart(2, '0')}:${date.getSeconds().toString().padStart(2, '0')}`;
        },
    },
    mounted: function() {
        setInterval(this.setTime, 1000);
    }
  }
</script>