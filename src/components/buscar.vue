<template>
  <v-data-table
      :headers="headers"
      :items="voluntarios"
      :single-expand="singleExpand"
      :expanded.sync="expanded"
      item-key="name"
      show-expand
      class="elevation-1"
  >
    <template v-slot:top>
      <v-toolbar flat>
        <v-toolbar-title>Habilidades de los Voluntarios</v-toolbar-title>
        <v-spacer></v-spacer>
       <!-- <v-switch v-model="singleExpand" label="Single expand" class="mt-2"></v-switch>-->
      </v-toolbar>
    </template>
    <template v-slot:expanded-item="{ headers, item }">
      <!--AQUI VAN LOS DATOS DEL EXPANDIBLE-->
      <td :colspan="headers.length">{{ item.desc }}</td>
    </template>
  </v-data-table>
</template>

<script>
export default {
  name: "buscar",
  data () {
    return {
      expanded: [],
      singleExpand: false,
      headers: [
        {
          text: 'Nombre',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: '', sortable: false, value: 'data-table-expand' },
      ],
      voluntarios: [
        {
          name: 'Ruben Ramirez',
          desc: "Carpintero, Conductor de maquinaria pesada",
        },
        {
          name: 'Marco de los Andes',
          desc: "Montañista, Salvavidas",
        },
        {
          name: 'Pepe Cortisona',
          desc: "Productor de alimentos",
        },
        {
          name: 'Carlos Diaz',
          desc: "Bombero",
        },
        {
          name: 'Ramon Alarcon',
          desc: "Experiencia en senderismo",
        },
        {
          name: 'Leandro Dominguez',
          desc: "Ingeniero en construccion, primeros auxilios",
        },
        {
          name: 'Jessie James',
          desc: "Trabajo en equipo, conocimientos de administracion de bodega",
        },
      ],
    }
  }

}
</script>

<style scoped>

</style>