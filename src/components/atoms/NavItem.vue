<template>
  <router-link class="item" :to="link" @click.native="scroll">
    <p class="text">{{ item.name }}</p>
    <hr class="line" />
  </router-link>
</template>

<style scoped>
.item {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  padding-top: 0.9rem;
  text-decoration: none;
  color: #ffffff;
  text-transform: uppercase;
  font-weight: 300;
  font-size: 1rem;
  letter-spacing: 0.05rem;
}

@media (min-width: 700px) and (orientation: portrait) {
  .item {
    padding: 0.9rem;
    padding-bottom: 0;
  }
}
@media (min-width: 900px) {
  .item {
    font-size: 1.3rem;
  }
}

.router-link-active {
  color: #ffd500;
  transition: color 0.4s 0.3s linear;
}

.text {
  margin: 0;
}

.line {
  width: 100%;
  border: 0;
  height: 1px;
  background-image: linear-gradient(
    to right,
    rgba(255, 213, 0, 0),
    rgba(255, 213, 0, 0.75),
    rgba(255, 213, 0, 0)
  );
  transform: scaleX(0);
  transition: transform 0.1s linear;
}

.router-link-active .line {
  transform: scaleX(1);
  transition: transform 0.4s 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
</style>

<script>
import { scrollTo } from "@/helpers";

export default {
  name: "NavItem",
  props: {
    item: Object
  },
  computed: {
    link: function() {
      return this.item.name === "projects"
        ? `/#${this.item.name}`
        : `/${this.item.name}`;
    }
  },
  methods: {
    scroll: function() {
      //to scroll to section on second click when path is already '#projects'
      if (this.item.name === "projects") {
        scrollTo("#projects", 1);
      }
    }
  }
};
</script>
