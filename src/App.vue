<template>
  <div id="app">
    <header class="header">
      <a href="#" class="header_logo">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 178 100">
          <use xlink:href="#icon_logo" />
        </svg>
      </a>
      <nav class="header__nav">
        <ul class="header__nav-ul">
          <li><a href="#collections">Подборки</a></li>
          <li><a href="#lists">Мои списки</a></li>
        </ul>
      </nav>
      <ThemeToggle />
    </header>
    <main>
      <h1></h1>
      <Collections />
      <Lists />
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
@import "~@/assets/variables.scss";

html {
  scroll-behavior: smooth;

  body {
    transition: all 400ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
    .svg__bank_unvisible {
      display: none;
    }

    .header {
      width: 100%;
      height: 100px;

      display: flex;
      position: relative;
      justify-content: space-around;
      align-items: center;

      * {
        max-height: 100%;
      }

      .header_logo {
        width: fit-content;
        height: 100%;
        * {
          height: 100%;
          width: auto;
          height: 100%;
        }
      }
      .header__nav {
        width: 50%;
        .header__nav-ul {
          box-sizing: border-box;
          padding: 0 1em;
          display: flex;
          width: 100%;
          justify-content: space-around;
          * {
            list-style: none;
            text-decoration: none;
            display: block;
            width: fit-content;
          }
        }
      }
    }
  }

  body {
    background: $bg-color;
  }

  body.dark_theme {
    $bg-color: black;
    $fg-color: whitesmoke;
    $color_prime: #1d3557;
    $color_second: #457b9d;

    background: $bg-color;
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
}

h1, h2, h3 {
  text-align: center !important;
}
</style>
