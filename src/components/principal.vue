<template>
  <div>
    <v-navigation-drawer
        v-model="drawer"
        app
        clipped
    >
      <v-list dense>
        <v-list-item link v-on:click= "mapFlag = !mapFlag">
          <v-list-item-action>
            <v-icon>mdi-map-marker-multiple</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Mapita {{mapFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "habFlag = !habFlag">
          <v-list-item-action>
            <v-icon>mdi-cow</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Habilidades voluntarios {{habFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "volFlag = !volFlag">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Voluntario {{volFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "haFlag = !haFlag">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Habilidad {{haFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "volhabFlag = !volhabFlag">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Vol-Hab {{volhabFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
        app
        clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Voluntariado</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container
          class="fill-height"
          fluid
      >
        <v-row
            align="center"
            justify="center"
        >
          <v-col class="shrink">
            <v-tooltip right>
            </v-tooltip>
          </v-col>
        </v-row>
        <Mapa></Mapa>
        askjdalksjdlaksjdas
      </v-container>
    </v-main>
    
    <div v-if= "mapFlag">
      mapflag
    </div>
    <div v-if="habFlag">
      habflag
    </div>
    <div v-if="volFlag">
      volflag
    </div>
    <div v-if="haFlag">
      haflag
    </div>
    <div v-if="volhabFlag">
      volhabflag
    </div>


  </div>
</template>

<script>
import Mapa from "@/components/mapa";
export default {
  name: "principal",
  components: {Mapa},
  props: {
    source: String,
  },
  data: () => ({
    drawer: null,
    mapFlag: null,
    habFlag: null,
    volFlag: null,
    haFlag: null,
    volhabFlag: null,
  }),
  created () {
    this.$vuetify.theme.dark = true
  }
}
</script>

<style scoped>

</style>