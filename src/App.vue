<template>
    <v-app id="inspire">
      <NavDrawer />
      <TopBar />

      <v-content>
        <v-container fluid fill-height>
          <v-layout align-center justify-center>
            <v-tooltip right>
              <template v-slot:activator="{ on }">
                <v-btn :href="source" icon large target="_blank" v-on="on">
                  <v-icon large>mdi-code-tags</v-icon>
                </v-btn>
              </template>
              <span>Source</span>
            </v-tooltip>
            <v-tooltip right>
              <template v-slot:activator="{ on }">
                <v-btn
                  icon
                  large
                  href="https://codepen.io/johnjleider/pen/MNYLdL"
                  target="_blank"
                  v-on="on"
                >
                  <v-icon large>mdi-codepen</v-icon>
                </v-btn>
              </template>
              <span>Codepen</span>
            </v-tooltip>
          </v-layout>
        </v-container>
      </v-content>
      <v-btn bottom color="pink" dark fab fixed right @click="dialog = !dialog">
        <v-icon>add</v-icon>
      </v-btn>
      <v-dialog v-model="dialog" width="800px">
        <v-card>
          <v-card-title class="grey darken-2">Create contact</v-card-title>
          <v-container grid-list-sm>
            <v-layout row wrap>
              <v-flex xs12 align-center justify-space-between>
                <v-layout align-center>
                  <v-avatar size="40px" class="mr-3">
                    <img src="//ssl.gstatic.com/s2/oz/images/sge/grey_silhouette.png" alt />
                  </v-avatar>
                  <v-text-field placeholder="Name"></v-text-field>
                </v-layout>
              </v-flex>
              <v-flex xs6>
                <v-text-field prepend-icon="business" placeholder="Company"></v-text-field>
              </v-flex>
              <v-flex xs6>
                <v-text-field placeholder="Job title"></v-text-field>
              </v-flex>
              <v-flex xs12>
                <v-text-field prepend-icon="mail" placeholder="Email"></v-text-field>
              </v-flex>
              <v-flex xs12>
                <v-text-field type="tel" prepend-icon="phone" placeholder="(000) 000 - 0000"></v-text-field>
              </v-flex>
              <v-flex xs12>
                <v-text-field prepend-icon="notes" placeholder="Notes"></v-text-field>
              </v-flex>
            </v-layout>
          </v-container>
          <v-card-actions>
            <v-btn text color="primary">More</v-btn>
            <v-spacer></v-spacer>
            <v-btn text color="primary" @click="dialog = false">Cancel</v-btn>
            <v-btn text @click="dialog = false">Save</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-app>
</template>

<script>

import NavDrawer from "./components/NavDrawer"
import TopBar from "./components/TopBar"
export default {
  name: "App",

  components: {
    NavDrawer,
    TopBar
  },

  data: () => ({
    dialog: false,
    drawer: null
  }),
};
</script>
