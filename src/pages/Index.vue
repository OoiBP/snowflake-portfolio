<template>
  <q-layout view="hHh lpr fff">
    <q-header>
      <q-toolbar>
        <q-toolbar-title class="font-russo"> Welcome </q-toolbar-title>

        <q-tabs v-model="tab" class="text-accent">
          <q-tab name="intro" label="Intro" @click="scrollToElement('intro')" />
          <q-tab name="about" label="About" @click="scrollToElement('about')" />
          <q-tab
            name="projects"
            label="Projects"
            @click="scrollToElement('projects')"
          />
          <q-tab
            name="contact"
            label="Contact"
            @click="scrollToElement('contact')"
          />
        </q-tabs>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <q-page>
        <section id="intro">
          <q-img src="../assets/background.jpg" height="85vh">
            <div class="absolute-full text-h1 flex flex-center font-russo">
              <transition appear enter-active-class="animated fadeInDown">
                <span> Hi,&nbsp; </span>
              </transition>
              <transition
                appear
                enter-active-class="animated lightSpeedInRight"
              >
                <span> I'm Wills </span>
              </transition>
            </div>
          </q-img>
        </section>

        <section id="about" class="q-py-xl">
          <div class="text-h3 text-center font-russo q-mb-lg">About Me</div>

          <div class="q-mb-xl">
            <AboutCard class="q-mx-auto" />
          </div>

          <div class="row">
            <div
              v-for="skill in skills"
              :key="skill.title"
              class="col-12 col-sm-6 col-md-3 q-mb-xl"
            >
              <SkillCard
                :icon="skill.icon"
                :title="skill.title"
                class="q-mx-auto"
              />
            </div>
          </div>
        </section>

        <section id="projects" class="q-py-xl bg-secondary">
          <div class="text-h3 text-center font-russo q-mb-lg">My Projects</div>

          <div class="row">
            <div
              v-for="project in projects"
              :key="project.title"
              class="col-12 col-sm-6 col-md-4 q-mb-xl"
            >
              <ProjectCard
                :image="project.image"
                :title="project.title"
                :subtitle="project.subtitle"
                :link="project.link"
                class="q-mx-auto"
              />
            </div>
          </div>
        </section>

        <section id="contact">
          <ContactForm />
        </section>
      </q-page>
    </q-page-container>

    <q-footer class="q-py-xs">
      <div class="flex justify-center">
        <q-btn
          v-for="item in footers"
          :key="item.name"
          flat
          round
          size="lg"
          :icon="item.icon"
          @click="goTo(item.link)"
        />
      </div>
    </q-footer>
  </q-layout>
</template>

<script>
import AboutCard from "src/components/AboutCard.vue";
import SkillCard from "src/components/SkillCard.vue";
import ProjectCard from "src/components/ProjectCard.vue";
import ContactForm from "src/components/ContactForm.vue";

import { scroll, openURL } from "quasar";
const { getScrollTarget, setScrollPosition } = scroll;

export default {
  name: "PageIndex",
  components: {
    AboutCard,
    SkillCard,
    ProjectCard,
    ContactForm,
  },
  data() {
    return {
      tab: "intro",
      skills: [
        {
          icon: "devices",
          title: "Web Development",
        },
        {
          icon: "memory",
          title: "Embedded System",
        },
        {
          icon: "cloud_upload",
          title: "Internet of Things",
        },
        {
          icon: "psychology",
          title: "Artificial Intelligence",
        },
      ],
      projects: [
        {
          image: "company.jpg",
          title: "Company Webpage",
          subtitle: "A simplistic company info webpage with basic animation",
          link: "https://ooibp.github.io/simple-company-webpage/",
        },
        {
          image: "euler.png",
          title: "Project Euler",
          subtitle:
            "My Github repo for solving Project Euler using Go language",
          link: "https://github.com/OoiBP/ProjectEuler",
        },
        {
          image: "dashboard.jpg",
          title: "IoT Dashboard",
          subtitle: "My ongoing dashboard monitoring project for IoT",
          link: "",
        },
      ],
      footers: [
        {
          name: "facebook",
          icon: "fab fa-facebook",
          link: "https://www.facebook.com/OoiBP92/",
        },
        {
          name: "github",
          icon: "fab fa-github",
          link: "https://github.com/OoiBP",
        },
        {
          name: "linkedin",
          icon: "fab fa-linkedin",
          link: "https://www.linkedin.com/in/boon-pin-ooi-715185194",
        },
      ],
    };
  },
  methods: {
    scrollToElement(id) {
      let el = document.getElementById(id);
      const target = getScrollTarget(el);
      const offset = el.offsetTop + 3;
      const duration = 300;
      setScrollPosition(target, offset, duration);
    },
    goTo(dest) {
      openURL(dest);
    },
  },
};
</script>

<style lang="scss">
.font-russo {
  font-family: "Russo One", sans-serif;
}

.font-ubuntu {
  font-family: "Ubuntu Mono", monospace;
}

.animated {
  animation-duration: 1.5s;
}
</style>
