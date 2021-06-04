<template>
  <section id="lists" style="text-align: center;">
    <h2>Списки</h2>
    <form action="" class="addTask">
      <input type="text" id="input_title" placeholder="Название"/>
      <select name="select_icon" id="select_icon">
        <option value="icon_css">CSS</option>
        <option value="icon_js">JS Библиотеки</option>
        <option value="icon_js2">JS Фреймворки</option>
      </select>
      <input type="number" name="input_priority" id="input_priority"  placeholder="Приоритет"/>
      <input
        type="reset"
        name="reset"
        id="btnAdd"
        value="Добавить"
        @click="addItem()"
      />
    </form>
    <div
      v-for="list in listNames"
      :key="list.id"
      @drop="onDrop($event, list.id)"
      class="lists__droppable"
      @dragover.prevent
      @dragenter.prevent
    >
      <h4>{{ list.title }}</h4>
      <div
        v-for="item in itemsData.filter((x) => x.listId === list.id)"
        @dragstart="onDragStart($event, item)"
        class="lists__draggable"
        draggable="true"
        :key="item.id"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="lists_img"
        >
          <use :xlink:href="'#'+item.icon" />
        </svg>
        <h5>{{ item.title }}</h5>
        <p>( {{item.priority}} )</p>
        <button class="check" @click="changePos(item.id, 1)" v-if="list.id!=1"></button>
        <!-- <button class="pencil"></button> -->
        <button class="cross" @click="deleteItem(item.id)"></button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Lists",
  data: function () {
    return {
      itemsData: [
        {
          id: 0,
          title: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse a turpis velit. Aliquam egestas nulla ante, quis fringilla metus pellentesque.",
          icon: "icon_css",
          priority: 2,
          listId: 0,
        },
        {
          id: 1,
          title: "Short text",
          icon: "icon_css",
          priority: 3,
          listId: 0,
        },
        {
          id: 2,
          title: "Lorem ipsum dolor sit",
          icon: "icon_css",
          priority: 1,
          listId: 1,
        },
      ],
      listNames: [
        {
          id: 0,
          title: "ToDo",
        },
        {
          id: 1,
          title: "Done",
        },
      ],
    };
  },
  methods: {
    changePos: function(itemId, listId) {
      this.itemsData = this.itemsData.map((x) => {
        if (x.id == itemId) x.listId = listId;
        return x;
      });
    },
    onDragStart: function (e, item) {
      e.dataTransfer.dropEffect = "move";
      e.dataTransfer.effectAllowed = "move";
      e.dataTransfer.setData("itemId", item.id.toString());
    },
    onDrop: function (e, listId) {
      const itemId = parseInt(e.dataTransfer.getData("itemId"));
      this.changePos(itemId, listId);
    },

    addItem: function () {
      let input_id = this.itemsData.lenght + 1;
      let input_title = document.getElementById("input_title").value;
      let input_icon = document.getElementById("select_icon").value;
      let input_priority = document.getElementById("input_priority").value;
      this.itemsData.push({
        id: input_id,
        title: input_title,
        icon: input_icon,
        priority: input_priority,
        listId: 0,
      });
    },
    deleteItem: function(itemId) {
      this.itemsData = this.itemsData.filter((x) => x.id != itemId)
    }
  },
};
</script>

<style>
.addTask {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;

  width: 100%;
  height: 100px;

  box-sizing: border-box;
  padding: 20px 0;
  font-size: 20px;
}

.addTask input,
.addTask select {
  height: 2.5em;
  box-sizing: border-box;
  font-size: inherit;
  margin: 10px;
}

.lists__draggable .check {
	right: 80px;
	background: url('~@/assets/img/check.svg') no-repeat, black;
}

.lists__draggable .pencil {
	background: url('~@/assets/img/pencil.svg') no-repeat, black;
}

.lists__draggable .cross {
	background: url('~@/assets/img/x.svg') no-repeat, black;
}

.lists__draggable button {
	height: 50px;
	width: 50px;
	border-radius: 100%;

	border: none;
	outline: none;

	background-size: 50% !important;
	background-position: center !important;

	transition: transform .1s, box-shadow .1s;
  margin: 5px;
  margin-right: 0;
}

.lists__draggable button:hover {
	cursor: pointer;
  transform: scale(1.05);
  box-shadow: 4px 4px 5px -5px var(--black);
}

.lists__droppable {
  vertical-align: top;
  display: inline-block;
  margin: 10px;

  width: 40%;
  min-width: 300px;
  padding: 15px;
  border-radius: 5px;
  margin-bottom: 10px;
}
.lists__draggable {
  padding: 5px;
  border-radius: 5px;
  margin-bottom: 5px;
  text-align: right;
}
.lists__draggable h5 {
  font-size: 30px;
  margin: 0;
}
.lists_img {
  height: 100px;
  width: 100px;
}
</style>