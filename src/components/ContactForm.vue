<template>
  <q-parallax src="../assets/parallax.jpg" :height="largeScreen ? 500 : 700">
    <div class="full-width">
      <div class="text-h3 text-center text-white font-russo q-mb-xl">
        Contact Me
      </div>

      <q-form class="full-width" @submit.prevent="">
        <div class="row">
          <div class="col-12 col-md-6 q-px-xl">
            <q-input
              v-model="name"
              outlined
              label="Your Name *"
              bg-color="white"
              color="secondary"
              class="q-mb-lg"
            />
            <q-input
              v-model="email"
              outlined
              type="email"
              label="Your Email *"
              bg-color="white"
              color="secondary"
              class="q-mb-lg"
            />
          </div>
          <div class="col-12 col-md-6 q-px-xl">
            <q-input
              v-model="subject"
              outlined
              label="Subject *"
              bg-color="white"
              color="secondary"
              class="q-mb-lg"
            />
            <q-input
              v-model="message"
              outlined
              type="textarea"
              label="Your Message *"
              bg-color="white"
              color="secondary"
              input-style="resize:none;"
            />
          </div>
        </div>

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
  </q-parallax>
</template>

<script>
export default {
  name: "ContactForm",
  data() {
    return {
      largeScreen: true,
      name: "",
      email: "",
      subject: "",
      message: ""
    };
  },
  watch: {
    "$q.screen.width"() {
      this.setScreen();
    }
  },
  mounted: function() {
    this.setScreen();
  },
  methods: {
    setScreen() {
      if (this.$q.screen.width < this.$q.screen.sizes.md) {
        this.largeScreen = false;
      } else {
        this.largeScreen = true;
      }
    }
  }
};
</script>
