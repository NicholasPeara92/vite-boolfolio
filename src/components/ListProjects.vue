<script>
import axios from "axios";
import CardProject from "./CardProject.vue";

export default {
  components: {
    CardProject,
  },
  data() {
    return {
      projects: [],
    };
  },
  created() {
    axios.get("http://127.0.0.1:8000/api/projects").then((response) => {
      this.projects = response.data;
    });
  },
};
</script>
<template>
  <section>
    <h2>Lista dei Progetti</h2>
    <div class="container">
      <div class="row gy-3">
        <div class="col-md-3" v-for="project in projects">
          <CardProject :data="project" />
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
