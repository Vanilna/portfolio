<template>
  <header class="header">
    <router-link to="/" class="logo-img"><logo /></router-link>
    <router-link to="/" class="logo-text">ALEX VYTIAHLOVSKA</router-link>
    <nav class="navItems">
      <NavItem v-for="item in items" :item="item" :key="item.index" />
    </nav>
  </header>
</template>
<script>
import NavItem from "@/components/atoms/NavItem.vue";
import Logo from "@/components/atoms/Logo.vue";

export default {
  name: "Navigation",
  components: { NavItem, Logo },
  data: () => {
    return {
      items: [
        { name: "projects", index: 0 },
        { name: "technologies", index: 1 },
        { name: "contact", index: 2 }
      ]
    };
  }
};
</script>
<style scoped>
.header {
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
  background-color: #141618;
  display: flex;
  flex-direction: column;
  padding: 0.8rem;
  align-items: center;
  padding-bottom: 1rem;
  z-index: 999;
  transition: all 0.5s 0.3s ease-out;
}
.logo-text {
  flex-basis: 80%;
  text-decoration: none;
  font-weight: 300;
  font-size: 1.3rem;
  color: #ffffff;
  flex-basis: 30%;
}

.logo-img {
  max-width: 100%;
  height: 7vh;
}
.navItems {
  width: 100%;
  display: flex;
  justify-content: space-evenly;
}
@media (min-width: 700px) and (orientation: portrait) {
  .navItems {
    max-width: 100%;
    width: auto;
  }
}
@media (orientation: landscape) and (min-aspect-ratio: 4/3) and (min-width: 500px) {
  .header {
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    margin: 0 auto;
  }
  .logo-img {
    flex-basis: 15%;
    height: 10vh;
  }
  .navItems {
    width: auto;
    flex-basis: 50%;
    margin-left: auto;
  }
}
@media (orientation: landscape) and (min-aspect-ratio: 4/3) and (min-width: 1000px) {
  .logo-text {
    font-size: 2rem;
    flex-basis: 30%;
  }
  .navItems {
    flex-basis: 40%;
  }
}
</style>
