<template>
  <div>
    <v-navigation-drawer
        v-model="drawer"
        app
        clipped
    >
      <v-list dense>
        <v-list-item link v-on:click= "manejarSeleccion('mapa')">
          <v-list-item-action>
            <v-icon>mdi-map-marker-multiple</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Mapita {{mapFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "manejarSeleccion('voluntarios')">
          <v-list-item-action>
            <v-icon>mdi-cow</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Habilidades voluntarios {{habFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "manejarSeleccion('crudVol')">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Voluntario {{volFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "manejarSeleccion('crudHab')">
          <v-list-item-action>
            <v-icon>mdi-folder-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>CRUD Habilidad {{haFlag}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link v-on:click= "manejarSeleccion('crud')">
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
      <v-toolbar-title>{{ titulo }}</v-toolbar-title>
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
      </v-container>
    </v-main>

    <v-container v-if="mapFlag" bg fill-height grid-list-md text-xs-center>
      <v-layout row wrap align-center>
        <v-flex>
          <Mapa></Mapa>
        </v-flex>
      </v-layout>
    </v-container>
    <v-container v-if="habFlag">

      <Buscar></Buscar>
    </v-container>

    <div v-if="volFlag">
      <!--<CrudV></CrudV>-->
    </div>
    <div v-if="haFlag">
      <!--<CrudH></CrudH>-->
    </div>
    <div v-if="volhabFlag">
      <!--<CrudVH></CrudVH>-->
    </div>


  </div>
</template>

<script>
import Mapa from "@/components/mapa";
import Buscar from "@/components/buscar";
//import CrudV from "@/components/crudV";
//import CrudH from "@/components/crudH";
//import CrudVH from "@/components/crudVH";


export default {
  name: "principal",
  components: {
    CrudV, Mapa, Buscar, //CrudV, CrudH, CrudVH,
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
    titulo: "Voluntariado",
  }),
  created () {
    this.$vuetify.theme.dark = true
  },
  methods: {
    manejarSeleccion: function(sel){
      switch (sel) {
        case 'mapa':
          this.mapFlag = true;
          this.habFlag = false;
          this.volFlag = false;
          this.haFlag = false;
          this.volhabFlag = false;
          this.titulo = "Mapa de voluntarios";
          break;
        case 'voluntarios':
          this.mapFlag = false;
          this.habFlag = true;
          this.volFlag = false;
          this.haFlag = false;
          this.volhabFlag = false;
          this.titulo = "Voluntarios: habilidades";
          break;
        case 'crudVol':
          this.mapFlag = false;
          this.habFlag = false;
          this.volFlag = true;
          this.haFlag = false;
          this.volhabFlag = false;
          this.titulo = "CRUD Voluntario";
          break;
        case 'crudHab':
          this.mapFlag = false;
          this.habFlag = false;
          this.volFlag = false;
          this.haFlag = true;
          this.volhabFlag = false;
          this.titulo = "CRUD Habilidad";
          break;
        case 'crud':
          this.mapFlag = false;
          this.habFlag = false;
          this.volFlag = false;
          this.haFlag = false;
          this.volhabFlag = true;
          this.titulo = "CRUD Voluntario-Habilidad";
          break;
        default:
          break;
      }
    }
  }
}
</script>

<style scoped>
.center {
  padding: 70px 0;
  border: 3px solid green;
  text-align: center;
}
</style>