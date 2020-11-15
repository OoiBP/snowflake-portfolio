<template>
  <q-card
    square
    @mouseover="hover = true"
    @mouseleave="hover = false"
    class="full-height"
    :class="{ 'shadow-12': hover }"
    style="width: 230px"
  >
    <q-card-section class="text-center">
      <q-icon :name="icon" size="100px" color="primary" />
    </q-card-section>
    <q-card-section>
      <div class="text-h5 text-center text-weight-bold text-secondary">
        {{ title }}
      </div>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  name: "SkillCard",
  props: {
    icon: String,
    title: String,
  },
  data() {
    return {
      hover: false,
    };
  },
};
</script>
