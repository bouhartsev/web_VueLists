<template>
  <section id="lists">
    <h2>Списки</h2>
    <form action="">
      <input type="text" id="input_title">
      <select name="select_icon" id="select_icon">
        <option value="icon_css">CSS</option>
        <option value="icon_js1">JS Библиотеки</option>
        <option value="icon_js2">JS Фреймворки</option>
      </select>
      <input type="number" name="input_priority" id="input_priority">
      <input type="reset" name="reset" id="btnAdd" value="Добавить" @click="addItem()">
    </form>
      <div
      v-for="list in listNames"
      :key="list.id"
      @drop="onDrop($event, list.id)"
      class="droppable"
      @dragover.prevent
      @dragenter.prevent
    >
      <h4>{{ list.title }}</h4>
      <div
        v-for="item in itemsData.filter((x) => x.listId === list.id)"
        @dragstart="onDragStart($event, item)"
        class="draggable"
        draggable="true"
        :key="item.id"
      >
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" class="collection_img">
        <use xlink:href="#{{}}" />
      </svg>
        <h5>{{ item.title }}</h5>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Lists',
  data: function () {
      return {
          itemsData: [
                {
                    id: 0,
                    title: 'Audi',
                    icon: "icon_css",
                    priority: 1,
                    listId: 0
                },
                {
                    id: 1,
                    title: 'BMW',
                    icon: "icon_css",
                    priority: 1,
                    listId: 0
                },
                {
                    id: 2,
                    title: 'Cat',
                    icon: "icon_css",
                    priority: 1,
                    listId: 1
                },
            ],
            listNames: [
                {
                    id: 0,
                    title: 'ToDo'
                },
                {
                    id: 1,
                    title: 'Done'
                }
            ],
      }
  },
  methods: {

    onDragStart: function (e, item) {
      e.dataTransfer.dropEffect = 'move';
      e.dataTransfer.effectAllowed = 'move';
      e.dataTransfer.setData('itemId', item.id.toString());
    },
    onDrop: function (e, listId) {
      const itemId = parseInt(e.dataTransfer.getData('itemId'));
      this.itemsData = this.itemsData.map(x => {
        if (x.id == itemId)
          x.listId = listId;
        return x;
      })
    },

    addItem: function() {
      let input_id = this.itemsData.lenght+1;
      let input_title = document.getElementById("input_title").value;
      let input_icon = document.getElementById("select_icon").value;
      let input_priority = document.getElementById("input_priority").value;
      this.itemsData.push({id: input_id, title: input_title, icon: input_icon, priority: input_priority, listId: 0});
    }
  }
}
</script>

<style scoped>
.droppable {
  display: inline-block;
  width: 40%;
  min-width: 300px;
  padding: 15px;
  border-radius: 5px;
  background: #2c3e50;
  margin-bottom: 10px;
}
.droppable h4 {
  color: white;
}
.draggable {
  background: white;
  padding: 5px;
  border-radius: 5px;
  margin-bottom: 5px;
}
.draggable h5 {
  margin: 0;
}
</style>