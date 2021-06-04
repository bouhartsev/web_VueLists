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
          <li><a href="#collections"><img class="nav__img" src="@/assets/img/internet_16px.png" srcset="@/assets/img/internet_64px.png 1x, @/assets/img/internet_512px.png 2x" alt="Clipboard"> Подборки</a></li>
          <li><a href="#lists"><img class="nav__img" src="@/assets/img/clipboard_16px.png" srcset="@/assets/img/clipboard_64px.png 1x, @/assets/img/clipboard_512px.png 2x" alt="Clipboard"> Cписки</a></li>
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
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,600;0,700;0,800;1,300;1,400;1,600;1,700;1,800&display=swap');

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
          .nav__img {
            display: inline-block;
            vertical-align: bottom;
            width: 32px;
            height: auto;
          }
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
      animation: scroll 20s infinite linear;
      overflow: hidden;
      will-change: transform;
    }
    @keyframes scroll {
    0% {
        transform: translate(100%, 0);
    }
    100% {
        transform: translate(-100%, 0)
    }
    }
    overflow-x: hidden;
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
    .lists__droppable {
      background: $color_three;
      h4 {
        color: $bg-color;
      }
    }
    .lists__draggable {
      background: $bg-color;
    }
  }

  body.dark_theme {
    $bg-color: black;
    $fg-color: whitesmoke;
    $color_prime: #1d3557;
    $color_second: #457b9d;
    $color_three: #F1FAEE;
    $color_four: #A8DADC;

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
    }
    .lists__droppable {
      background: $color_three;
      * {
        color: $bg-color;
      }
    }
    .lists__draggable {
      background: $color_four;
    }
  }
}

#app {
  font-family: 'Open Sans', sans-serif;
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

@media (max-width: 400px) {
  body {
    font-size: 14px;
  }
}
</style>
