<template>
  <v-container fluid>
    <div>
      <v-row no-gutters class="d-flex justify-space-between mt-10 mb-6">
        <h1 class="page-title">Projetos que participo</h1>
      </v-row>
      <List :items="items"></List>
    </div>
  </v-container>
</template>

<script>
import List from "../../components/List/List.vue";
export default {
  name: "Colaborate",
  components: { List },
  data() {
    return {
      items: [
        //TODO step será as etapas em que os projetos se encontram 0 = em andamento, 1 = finalizado, 2 = pausado
        { text: "Projeto tech blog", step: 0 },
        { text: "Projeto software para automóveis ", step: 1 },
        { text: "software para a área pet", step: 2 },
      ],
    };
  },
};
</script>
