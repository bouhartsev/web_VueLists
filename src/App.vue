<template>
  <div id="app">
    <header>
      <a href="#">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 178 100">
          <use xlink:href="#icon_logo" />
        </svg>
      </a>
      <!-- logo -->
      <nav>
        <ul>
          <li><a href="#collections">Подборки</a></li>
          <li><a href="#lists">Мои списки</a></li>
        </ul>
      </nav>
      <ThemeToggle />
      <Collections />
      <Lists />
    </header>
    <main>
      <h1></h1>
      <section></section>
    </main>
    <footer>Бухарцев Матвей Александрович, 201-321, 04.06.2021</footer>
  </div>
</template>

<script>
import ThemeToggle from "@/components/ThemeToggle.vue";
import Collections from "@/components/Collections.vue";
import Lists from "@/components/Lists.vue";

export default {
  name: "App",
  components: {
    ThemeToggle,
    Collections,
    Lists,
  },
};
</script>

<style lang="scss">
@import '~@/assets/variables.scss';

html {
  scroll-behavior: smooth;

  body.dark_theme {
    background: $bg-color;

    .svg__bank_unvisible {
      display: none;
    }
  }
  
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
}
</style>
