<template>
  <v-app>
    <v-main>
      <Header/>
      <HelloWorld/>
      <Link/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Header from './components/Header';
import Link from './components/Link';

export default {
  name: 'App',

  components: {
    HelloWorld,
    Header,
    Link,
  },

  data: () => ({
    //
  }),
};
</script>
