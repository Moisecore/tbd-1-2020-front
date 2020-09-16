<template>
  <div>
    <v-navigation-drawer
        v-model="drawer"
        app
        clipped
    >
      <v-list dense>
        <v-list-item link v-on:click= "aux = 1">
          <v-list-item-action>
            <v-icon>mdi-map-marker-multiple</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Mapita {{mapFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "aux = 2">
          <v-list-item-action>
            <v-icon>mdi-cow</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Habilidades voluntarios {{habFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "aux = 3">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Voluntario {{volFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "aux = 4">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Habilidad {{haFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "aux = 5">
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
        <!--<Mapa></Mapa>
        askjdalksjdlaksjdas-->
      </v-container>
    </v-main>

    <v-container v-if="mapFlag" bg fill-height grid-list-md text-xs-center>
      <v-layout row wrap align-center>
        <v-flex>
          <Mapa></Mapa>
        </v-flex>
      </v-layout>
    </v-container>

    <!--<Mapa v-if="mapFlag" ></Mapa> -->
    <v-container v-if="habFlag">
      <Buscar></Buscar>
    </v-container>

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
import Buscar from "@/components/buscar";
export default {
  name: "principal",
  components: { Mapa, Buscar
  },
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
  },
  methods: {
    manejarSeleccion: function(sel){
      switch (sel) {
        case 'mapa':
          mapFlag: true;
          habFlag: false;
          volFlag: false;
          haFlag: false;
          volhabFlag: false;
          break;
        case 'voluntarios':
          mapFlag: false;
          habFlag: true;
          volFlag: false;
          haFlag: false;
          volhabFlag: false;
          break;
        case 'crudVol':
          mapFlag: false;
          habFlag: false;
          volFlag: true;
          haFlag: false;
          volhabFlag: false;
          break;
        case 'crudHab':
          mapFlag: false;
          habFlag: false;
          volFlag: false;
          haFlag: true;
          volhabFlag: false;
          break;
        case 'crud':
          mapFlag: false;
          habFlag: false;
          volFlag: false;
          haFlag: false;
          volhabFlag: true;
          break;
        default:
          break;
      }
    }
  }
}
</script>

<style scoped>

</style>