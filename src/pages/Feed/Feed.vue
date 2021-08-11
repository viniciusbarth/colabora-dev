<template>
  <v-container fluid>
    <div >
      <v-row no-gutters class="d-flex justify-space-between mt-10 mb-6">
        <h1 class="page-title">Feed de projetos</h1>
      <v-spacer></v-spacer>
      <v-btn color="primary"><v-icon>mdi-plus</v-icon>Criar proposta</v-btn>
      </v-row>

      <v-row>
        <v-col cols="12" v-for="(post, index) in mock.posts" :key="index">
          <Post :post="post"></Post>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
import mock from "./mock";
import Post from './Post'

export default {
  name: "Feed",
  components: {
    Post
  },
  data() {
    return {
      mock
    };
  }
};
</script>

<style src="./Feed.scss" lang="scss"/>
