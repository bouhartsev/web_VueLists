<template>
  <section id="lists">
    <h2>Списки</h2>
    <form action="">
      <select name="" id="">
        <option value="">CSS</option>
        <option value="">JS Библиотеки</option>
        <option value="">JS Фреймворки</option>
      </select>
      <input type="text">
    </form>
      <div
      v-for="list in categories"
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
                    listId: 0
                },
                {
                    id: 1,
                    title: 'BMW',
                    listId: 0
                },
                {
                    id: 2,
                    title: 'Cat',
                    listId: 1
                },
            ],
            categories: [
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
    }
  }
}
</script>

<style scoped>
.droppable {
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