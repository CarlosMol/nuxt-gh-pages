<template>
  <v-flex xs12>
    <v-layout row>
      <v-flex xs5>
        <v-card elevation="0">
          <v-card-title class="align-center justify-center">Texto Original</v-card-title>
          <v-card-text>
            <v-textarea filled></v-textarea>
          </v-card-text>
        </v-card>
      </v-flex>
      <v-flex xs2>
        <br />
        <br />
        <br />
        <br />
        <br />
        <v-layout align-center justify-center>
          <v-btn>comparar</v-btn>
        </v-layout>
      </v-flex>
      <v-flex xs5>
        <v-card elevation="0">
          <v-card-title class="align-center justify-center">Texto Modificado</v-card-title>
          <v-card-text>
            <v-textarea filled></v-textarea>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-flex>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo
  }
};
</script>
