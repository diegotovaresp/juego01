<template>
  <v-app>

    <v-main>
      <juego1/>
    </v-main>
  </v-app>
</template>

<script>
import juego1 from './components/Juego1';

export default {
  name: 'App',

  components: {
    juego1,
  },

  data: () => ({
    //
  }),
};
</script>
