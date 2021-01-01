<template>
  <v-card>
    <v-list-item>
      <v-list-item-content>
        <div class="text-center">

          <v-tooltip top>
                <template v-slot:activator="{ on, attrs }">
                    <v-btn
                    class="mx-2"
                    fab
                    dark
                    large
                    color="grey"
                    v-bind="attrs"
                    v-on="on"
                    v-on:click="discord"
                    >
                        <v-icon>
                            mdi-discord
                        </v-icon>
                    </v-btn>
                </template>
                <span>Discord</span>
            </v-tooltip>

            <v-tooltip top>
                <template v-slot:activator="{ on, attrs }">
                    <v-btn
                    class="mx-2"
                    fab
                    dark
                    large
                    color="cyan"
                    v-bind="attrs"
                    v-on="on"
                    v-on:click="telegram"
                    >
                        <v-icon>
                            mdi-telegram
                        </v-icon>
                    </v-btn>
                </template>
                <span>Telegram</span>
            </v-tooltip>

        </div>
      </v-list-item-content>
    </v-list-item>
  </v-card>
</template>

<script>
  export default {
    name: 'Link',
    methods: {
        telegram() {
            window.open('https://t.me/EgaNoobMinecraftServerWatcher', '_blank');
        },
        discord() {
          window.open('https://discord.gg/87P7hFnWen', '_blank');
        }
    }
  }
</script>