<template>
  <v-container fluid>
    <div>
      <v-row no-gutters class="d-flex justify-space-between mt-10 mb-6">
        <h1 class="page-title">Projetos que participo</h1>
      </v-row>
      <List></List>
    </div>
  </v-container>
</template>

<script>
import List from "../../components/List/List.vue";
export default {
  name: "Colaborate",
  components: { List },
  data() {
    return {};
  },
};
</script>
