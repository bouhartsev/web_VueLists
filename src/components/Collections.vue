<template>
  <section id="collections">
    <div class="collection__card">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
        <use xlink:href="#icon_css" />
     </svg>
      <h3>CSS</h3>
      <ul>
        <li class="collection__item">
          <h4 class="collection__item_heading">Bootstrap</h4>
          <p class="collection__item_description">
            Эту платформу создали в Twitter в 2011 году, чтобы сделать
            адаптивный дизайн доступным для разработчиков. С тех пор проект
            развился и предлагает бесчисленное множество функций для повышения
            производительности интерфейса.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">Foundation</h4>
          <p class="collection__item_description">
            Foundation – идеальный выбор для опытных разработчиков, которым
            нравится свобода действий. Это не просто библиотека CSS, а скорее
            семейство инструментов для разработки внешнего интерфейса. Их можно
            использовать вместе или полностью независимо.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">Bulma</h4>
          <p class="collection__item_description">
            Bulma – отличная альтернатива Bootstrap с современным кодом и
            уникальной эстетикой. Инструментарий отличается простым синтаксисом,
            изобилует готовыми компонентами, к тому же его легко импортировать в
            проекты.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">Tailwind</h4>
          <p class="collection__item_description">
            Tailwind не имеет определенного дизайна, но позволяет быстрее
            реализовать собственный уникальный стиль: с ним практически не
            требуется писать свойства CSS вручную. Опытные разработчики
            интерфейсов широко используют мощные функции инструментария в
            проектах.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">Pure</h4>
          <p class="collection__item_description">
            Крошечная библиотека с открытым исходным кодом от Yahoo, которая при
            использовании всех модулей занимает 3,7 КБ (в сжатом виде). Pure
            предлагает многоразовые отзывчивые модули CSS, которые можно
            добавить в любой веб-проект.
          </p>
        </li>
      </ul>
    </div>
    <div class="collection__card">
      <h3>JS Библиотеки</h3>
      <ul>
        <li class="collection__item">
          <h4 class="collection__item_heading">jQuery</h4>
          <p class="collection__item_description">
            Набор функций для манипуляций с DOM, работы с событиями и модуль для клиент-серверного взаимодействия.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">D3</h4>
          <p class="collection__item_description">
            Библиотека для создания визуализаций с использованием SVG.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">React</h4>
          <p class="collection__item_description">
           Библиотека для отображения данных и управлению DOM деревом.
          </p>
        </li>
      </ul>
    </div>
    <div class="collection__card">
      <h3>JS Фреймворки</h3>
      <ul>
        <li class="collection__item">
          <h4 class="collection__item_heading">AngularJS</h4>
          <p class="collection__item_description">
            Фреймворк для создания SPA, включает в себя инструменты для разработки и тестирования, реализует архитектуры MVC и MVVM, имеет открытый исходный код.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">Vue.js</h4>
          <p class="collection__item_description">
            Также фреймворк для создания SPA, реализует шаблон MVVM, имеет открытый исходный код.
          </p>
        </li>
        <li class="collection__item">
          <h4 class="collection__item_heading">Ember.js</h4>
          <p class="collection__item_description">
            Ещё один фреймворк для создания SPA с открытым кодом, который реализует шаблон MVC.
          </p>
        </li>
      </ul>
    </div>
    
  </section>
</template>

<script>
export default {
  name: "Collections",
  data: function () {
    return {
      //
    };
  },
  methods: {
    //
  },
};
</script>

<style scoped>
</style>