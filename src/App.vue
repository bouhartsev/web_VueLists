<template>
  <div id="app">
    <header>
      <img alt="Vue logo" src="./assets/logo.png">
      <!-- logo -->
      <nav>
        <ul>
          <li><a href=""></a></li>
        </ul>
      </nav>
      <ThemeToggle />
      <List></List>
    </header>
    <main>
      <h1></h1>
      <section></section>
    </main>
    <footer>Бухарцев Матвей Александрович, 201-321, 04.06.2021</footer>
  </div>
</template>

<script>
import ThemeToggle from '@/components/ThemeToggle.vue'
import List from '@/components/List.vue'

export default {
  name: 'App',
  components: {
    ThemeToggle,
    List,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
