<template>
  <div class="containet">
    <h2>ToDoList</h2>
    <div class="tte">
      <input v-model="value" class="input_text" type="text" placeholder="Title..." />
      <button @click="sendData()">Add</button>
    </div>
    <div class="list_containet">
      <div class="list_items">
        <div v-if="insertData.length == 1">1 element</div>
        <TodoItem
          v-for="(el, index) in insertData"
          :delateData="delateData"
          :key="index"
          :mess="el"
          :index="index"
        />
      </div>
    </div>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue";
export default {
  components: { TodoItem },
  data() {
    return {
      insertData: [],
      value: "",
    };
  },
  methods: {
    sendData() {
      if (this.value === "") return;
      this.insertData.push({
        mes: this.value,
      });
      this.value = "";
    },
    delateData(index) {
      this.insertData.splice(index, 1);
    },
  },
};
</script>

<style></style>
