<template>
  <section class="projectWrapper">
    <a :href="project.web" target="_blank" class="prevue">
      <img :src="project.img" :alt="project.name" class="prevue__img" />
    </a>
    <div class="lead">
      <h2 class="title">{{ project.name }}</h2>
      <project-technologies :technologies="project.technologies" />
    </div>
    <article class="content">
      <div v-html="project.description"></div>
      <web-buttons :code="project.code" :web="project.web" />
    </article>
  </section>
</template>

<script>
import ProjectTechnologies from "@/components/atoms/ProjectTechnologies.vue";
import WebButtons from "@/components/atoms/WebButtons.vue";

export default {
  name: "Project",
  props: {
    project: {
      name: String,
      technologies: Array,
      description: String,
      web: String,
      code: String,
      img: String
    }
  },
  components: {
    ProjectTechnologies,
    WebButtons
  }
};
</script>

<style scoped>
.projectWrapper {
  border: 1px solid #ffd500;
  border-radius: 0.5rem;
  background-color: transparent;
  margin: 3rem 1rem 0;
  width: calc(100% - 2rem);
  padding: 1rem;
  box-shadow: 5px 5px 7px rgba(255, 255, 255, 0.05);
}
.prevue {
  position: relative;
  top: -4rem;
  width: 100%;
  margin: 0 auto;
}
.prevue__img {
  border-radius: 0.5rem;
  width: 100%;
  box-shadow: 5px 5px 7px rgba(255, 255, 255, 0.05);
}
.lead {
  margin-top: -4rem;
}
.title {
  font-size: 1.5rem;
  font-weight: 300;
  color: #ffffff;
  text-transform: uppercase;
}
@media (orientation: landscape) and (min-width: 1000px) {
  .projectWrapper {
    margin: 3rem 5rem 0 0;
    width: calc(100% - 5rem);
    padding: 1.5rem;
    display: grid;
    grid-template-columns: 2fr 5fr;
  }
  .prevue {
    position: static;
    grid-column: 2 / 3;
    grid-row: 1 / 2;
    justify-self: end;
    margin: -4.5rem -4.5rem 0 0;
    width: 100%;
  }
  .lead {
    grid-column: 1 / 2;
    grid-row: 1 / 2;
    margin-top: 0;
    margin-right: -4rem;
  }
  .content {
    grid-column: 1 / -1;
  }
  .title {
    margin-top: 0;
  }
}
</style>
