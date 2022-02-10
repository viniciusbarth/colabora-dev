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
          <slot name="action" />
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
    };
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
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
