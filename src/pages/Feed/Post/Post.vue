<template>
  <v-card @click="clickedCard(post)">
    <v-card-title
      >{{ post.title }}
      <v-spacer></v-spacer>
      <v-btn
        class="mx-1"
        v-for="(tags, index) in post.tags"
        :key="index"
        style="color: black; border: 1px solid grey; padding: 5px; border-radius: 10px"
        >{{ tags }}</v-btn
      >
    </v-card-title>
    <v-card-subtitle>
      <v-row>
        <v-col cols="12" class="font-weight-black">
          {{ post.author }}
        </v-col>
      </v-row>
    </v-card-subtitle>
    <v-card-text>
      {{ post.description }}
    </v-card-text>
    <v-card-actions class="pr-4">
      <span>Qtd. pessoas no projeto: {{ post.qtdColaborates }}</span>
      <v-spacer></v-spacer>
      <v-btn color="success">Interesse no projeto</v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  props: {
    post: {
      type: Object,
      default: () => {},
    },
  },
  methods: {
    clickedCard(post) {
      this.$emit("click", post);
    },
  },
};
</script>
