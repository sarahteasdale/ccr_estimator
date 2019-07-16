<template>
  <v-app>
    <!-- <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar> -->


    <v-toolbar app color="white" >
      <v-spacer></v-spacer>
      <v-toolbar-title> <h1 class="display-1 font-weight-bold">CCS Calculator</h1> </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    
    <v-content>
      <v-container fluid grid-list-md text-xs-center pa-0>
        <v-layout row wrap pa-0>
          <v-flex xs12 pa-0>
            <v-card>
              <v-card-text>(Please Choose One...)</v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
      <!-- <Form/> -->
      <CalculatorForm/>
    </v-content>
  </v-app>
</template>

<script>
//import Form from './components/Form.vue'
import CalculatorForm from './components/CalculatorForm.vue'

export default {
  name: 'App',
  components: {
    //Form,
    CalculatorForm
  },
  data () {
    return {
      //
    }
  }
}
</script>

<style scoped>
h1 {
  color: #9C897A;
  font-family: Chevin Pro;
}
</style>
