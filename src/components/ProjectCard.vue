<template>
  <q-card
    class="zoom full-height"
    :class="{ 'shadow-12': hover }"
    @mouseover="hover = true"
    @mouseleave="hover = false"
    style="width:230px"
  >
    <q-img :src="`./projects/${image}`" height="160px" />

    <q-card-section>
      <div class="text-h6">{{ title }}</div>
    </q-card-section>

    <q-card-section class="q-pt-none">
      {{ subtitle }}
    </q-card-section>

    <q-card-actions v-if="link !== ''" align="right">
      <a :href="link" target="_blank" class="link text-subtitle2 text-primary"
        >Visit website >></a
      >
    </q-card-actions>
  </q-card>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    image: String,
    title: String,
    subtitle: String,
    link: String
  },
  data() {
    return {
      hover: false
    };
  }
};
</script>

<style lang="scss" scoped>
.zoom:hover {
  transform: scale(1.1);
}

.link {
  text-decoration: none;
}
</style>
