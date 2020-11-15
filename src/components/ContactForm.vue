<template>
  <q-parallax src="../assets/parallax.jpg" :height="600">
    <div class="full-width">
      <div class="text-h3 text-center text-white font-russo">Contact Me</div>

      <div
        class="q-mx-auto q-mt-xl"
        :style="{ width: largeScreen ? '50%' : '90%' }"
      >
        <q-form
          class="bg-opacity rounded-corner q-pa-lg"
          @submit.prevent="sendMail"
        >
          <q-input
            v-model="subject"
            outlined
            label="Subject *"
            bg-color="white"
            color="secondary"
            class="q-mb-lg"
            :rules="[(val) => !!val || '* Required']"
          />
          <q-input
            v-model="message"
            outlined
            type="textarea"
            label="Your Message *"
            bg-color="white"
            color="secondary"
            input-style="resize:none;"
            :rules="[(val) => !!val || '* Required']"
          />

          <div class="flex justify-center q-mt-xl">
            <q-btn
              type="submit"
              label="Send Message"
              size="lg"
              color="positive"
            />
          </div>
        </q-form>
      </div>
    </div>
  </q-parallax>
</template>

<script>
export default {
  name: "ContactForm",
  data() {
    return {
      largeScreen: true,
      subject: "",
      message: "",
    };
  },
  watch: {
    "$q.screen.width"() {
      this.setScreen();
    },
  },
  mounted: function () {
    this.setScreen();
  },
  methods: {
    setScreen() {
      if (this.$q.screen.width < this.$q.screen.sizes.md) {
        this.largeScreen = false;
      } else {
        this.largeScreen = true;
      }
    },
    sendMail() {
      window.location.href = `mailto:bp_ooi0702@hotmail.com?subject=${this.subject}&body=${this.message}`;

      subject = "";
      message = "";
    },
  },
};
</script>

<style lang="scss" scoped>
.bg-opacity {
  background-color: rgba(255, 255, 255, 0.7);
}
.rounded-corner {
  border-radius: 4px;
}
</style>