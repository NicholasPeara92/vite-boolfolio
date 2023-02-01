<script>
import axios from "axios";
import AppCard from "./AppCard.vue";

export default {
  components: {
    AppCard,
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
    <div class="container">
      <h2>Lista dei Progetti</h2>
      <ul>
        <li v-for="project in projects">
          {{ project.title }}
        </li>
      </ul>
    </div>
    <AppCard />
  </section>
</template>

<style lang="scss" scoped></style>
