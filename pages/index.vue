<template>
  <v-container>
    <v-flex xs12>
      <v-layout row>
        <v-flex xs5>
          <v-card elevation="0">
            <v-card-title class="align-center justify-center">Texto Original</v-card-title>
            <v-card-text>
              <v-textarea v-model="text1" filled></v-textarea>
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
            <v-btn @click="comparar">comparar</v-btn>
          </v-layout>
        </v-flex>
        <v-flex xs5>
          <v-card elevation="0">
            <v-card-title class="align-center justify-center">Texto Modificado</v-card-title>
            <v-card-text>
              <v-textarea v-model="text2" filled></v-textarea>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-flex>
    <br />
    <br />
    <v-flex xs12>
      <v-card elevation="0">
        <v-card-title class="align-left justify-left">Resultado</v-card-title>
        <v-card-text>
          <div id="outputdiv" style="font-size:1.4rem"></div>
        </v-card-text>
      </v-card>
    </v-flex>
  </v-container>
</template>

<script>
import diff_match from "~/components/diff_match_patch";

export default {
  components: {
    diff_match
  },
  data() {
    return {
      text1: "",
      text2: "",
      textoIgual: ""
    };
  },
  methods: {
    comparar() {
      try {
        let aux = diff_match.diff_match_patch.prototype.diff_main(
          this.text1,
          this.text2,
          false
        );
        // console.log(aux);
        // this.textoIgual = aux.filter(o => o[0] == -1);
        let aux2 = diff_match.diff_match_patch.prototype.diff_prettyHtml(aux);
        document.getElementById("outputdiv").innerHTML = aux2;
      } catch (error) {
        console.log(error);
      }
    }
  }
};
</script>
