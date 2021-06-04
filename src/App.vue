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
    <main class="main">
      <h1>ИЗУЧАЕМ ВЕБ-РАЗРАБОТКУ</h1>
      <Collections />
      <Lists />
    </main>
    <footer class="footer">Бухарцев Матвей Александрович, 201-321, 04.06.2021</footer>
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
    .svg__bank_unvisible {
      display: none;
    }

    .header {
      position: fixed;
      top: 0px;
      left: 0px;
      z-index: 10;

      width: 100%;
      min-height: 100px;

      display: flex;
      justify-content: space-around;
      align-items: center;
      align-content: center;
      flex-wrap: wrap;

      padding: 10px 0;

      * {
        max-height: 100%;
      }

      .header_logo {
        width: fit-content;
        height: 100px;
        * {
          height: 100%;
          width: auto;
          height: 100%;
        }
      }
      .header__nav {
        min-width: 50%;
        width: 300px;
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
            color: inherit;
          }
          text-transform: uppercase;
          font-size: 1.2em;
        }
      }
    }
    .main {
      margin-top: 300px;
    }
    .footer {
      width: 100%;
      text-align: center;
      margin-top: 50px;
    }
  }

  body {
    background: $bg-color;
    color: $fg-color;

    .header {
      background: $color_second;
      * {
        fill: $fg-color;
      }
    }

    .collection__card {
      background: $color_prime;
      // color: $
    }
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
}

h1,
h2,
h3 {
  text-align: center !important;
}

section {
  padding-top: 150px;
}
</style>
