<template>
  <v-data-table
      :headers="headers"
      :items="desserts"
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
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Calories', value: 'calories' },
        { text: 'Fat (g)', value: 'fat' },
        { text: 'Carbs (g)', value: 'carbs' },
        { text: 'Protein (g)', value: 'protein' },
        { text: 'Iron (%)', value: 'iron' },
        { text: '', value: 'data-table-expand' },
      ],
      desserts: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: '1%',
          desc: "Frozz",
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: '1%',
          desc: "Icee",
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: '7%',
          desc: "Eclaireclaire",
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: '8%',
          desc: "Q-kake",
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: '16%',
          desc: "Ginger-Shrek",
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: '0%',
          desc: "Jelly-Dolphin",
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: '2%',
          desc: "Lolicucked",
        },
        {
          name: 'Honeycomb',
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          iron: '45%',
          desc: "Miel Gibson",
        },
        {
          name: 'Donut',
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          iron: '22%',
          desc: "DonKin Kon",
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: '6%',
          desc: "KIH-KAH",
        },
      ],
    }
  },
  methods: {
    hiceClick: function(){
      this.console.log("hice click")
    }
  }
}
</script>

<style scoped>

</style>