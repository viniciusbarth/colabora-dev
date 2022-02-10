<template>
  <v-container fluid>
    <div>
      <v-row no-gutters class="d-flex justify-space-between mt-10 mb-6">
        <h1 class="page-title">Feed de projetos</h1>
        <v-spacer></v-spacer>
        <v-btn color="primary" @click="openNewProject"
          ><v-icon>mdi-plus</v-icon>Criar projeto</v-btn
        >
      </v-row>

      <v-row>
        <v-col cols="12" v-for="(post, index) in mock.posts" :key="index">
          <Post :post="post" @click="(post) => openDetails(post)" />
        </v-col>
      </v-row>
    </div>
    <new-project v-model="isNewProject" @close="closeModal"></new-project>
  </v-container>
</template>

<script>
import mock from "./mock";
import Post from "./Post/Post";
import newProject from "./new-project/new-project.vue";

export default {
  name: "Feed",
  components: {
    Post,
    newProject,
  },
  data() {
    return {
      mock,
      isNewProject: false,
    };
  },
  methods: {
    openNewProject() {
      this.isNewProject = true;
    },
    closeModal() {
      this.isNewProject = false;
    },
    openDetails() {
      this.$router.push({ name: "details" });
    },
  },
};
</script>

<style src="./Feed.scss" lang="scss" />
