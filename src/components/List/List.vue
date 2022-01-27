<template>
  <v-list flat class="dev-list">
    <v-list-item-group v-model="selectedItem" color="primary">
      <v-list-item
        class="dev-list__list-item"
        v-for="(item, i) in items"
        :key="i"
      >
        <v-list-item-icon>
          <v-icon>{{ getIcon(item.step) }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.text }}</v-list-item-title>
        </v-list-item-content>
        <v-list-item-action>
          <p>teste</p>
        </v-list-item-action>
      </v-list-item>
    </v-list-item-group>
  </v-list>
</template>
<script>
export default {
  data() {
    return {
      selectedItem: 0,
      items: [
        //TODO step será as etapas em que os projetos se encontram 0 = em andamento, 1 = finalizado, 2 = pausado
        { text: "Projeto tech blog", step: 0 },
        { text: "Projeto software para automóveis ", step: 1 },
        { text: "software para a área pet", step: 2 },
      ],
    };
  },
  computed: {},
  methods: {
    getIcon(icon) {
      const icons = {
        0: "mdi-clock-time-five",
        1: "mdi-check",
        2: "mdi-pause-circle",
      };
      return icons[icon];
    },
  },
};
</script>
<style lang="scss" scoped>
.dev-list {
  background-color: transparent;
  &__list-item {
    background-color: white;
    margin-top: 8px;
  }
}
</style>
