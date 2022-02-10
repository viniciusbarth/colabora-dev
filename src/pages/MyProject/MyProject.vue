<template>
  <v-container fluid>
    <div>
      <v-row no-gutters class="d-flex justify-space-between mt-10 mb-6">
        <h1 class="page-title">Meus Projetos</h1>
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
      items: [{ text: "Projeto que pensei finalizado", step: 0 }],
    };
  },
};
</script>
