<template>
  <q-card dark style="min-width:430px; max-width:80%">
    <q-bar>
      <q-btn dense flat round icon="lens" size="8.5px" color="red" />
      <q-btn dense flat round icon="lens" size="8.5px" color="yellow" />
      <q-btn dense flat round icon="lens" size="8.5px" color="green" />
      <div class="col text-center text-weight-bold">
        Greeting
      </div>
    </q-bar>

    <q-card-section :horizontal="largeScreen">
      <div style="width:300px; " class="q-mx-auto">
        <q-img
          src="../assets/my_pic.jpg"
          width="300px"
          style="border-radius:inherit"
        />
      </div>

      <q-card-section class="full-width font-ubuntu">
        <div class="text-h4 text-weight-bold text-negative text-center">
          <span class="text-info">&#60;</span>Software Engineer
          <span class="text-info">/&#62;</span>
        </div>

        <div class="text-subtitle1">
          <span class="text-info">{</span>
          <br />
          &nbsp;&nbsp;<span class="text-negative">"name": </span>
          <span>"Ooi Boon Pin",</span>
          <br />

          &nbsp;&nbsp;<span class="text-negative">"country": </span>
          <span>"Malaysia",</span>
          <br />

          &nbsp;&nbsp;<span class="text-negative">"email": </span>
          <span>"bp_ooi0702@hotmail.com",</span>
          <br />

          &nbsp;&nbsp;<span class="text-negative">"languages": </span>
          <span>[</span>
          <br />
          &nbsp;&nbsp;&nbsp;&nbsp;<span>"JavaScript",</span><br />
          &nbsp;&nbsp;&nbsp;&nbsp;<span>"Python",</span><br />
          &nbsp;&nbsp;&nbsp;&nbsp;<span>"Go",</span><br />
          &nbsp;&nbsp;&nbsp;&nbsp;<span>"Dart"</span><br />
          &nbsp;&nbsp;<span>]</span>
          <br />

          <span class="text-info">}</span>
        </div>
      </q-card-section>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  name: "AboutCard",
  data() {
    return {
      largeScreen: true
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
