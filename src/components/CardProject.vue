<script>
export default {
  name: "AppCard",
  props: {
    data: Object,
  },
  methods: {
    truncateText(text) {
      return text.substring(0, 250) + "...";
    },
  },
};
</script>

<template>
  <div class="card" style="width: 18rem">
    <img
      v-if="data.image_url"
      :src="data.image_url"
      class="card-img-top"
      :alt="data.title"
    />
    <div class="card-body">
      <h5 class="card-title">{{ data.title }}</h5>
      <p class="card-text">
        {{ truncateText(data.description) }}
      </p>
      <a href="#" class="btn btn-primary">Leggi di più</a>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
