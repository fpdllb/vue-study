<template>
  <div id="app">
    <div><input v-model="inputValue" /> <button @click="handleSubmit">submit</button></div>
    <ul>
      <todo-item
        v-for="(item, index) in list"
        :content="item"
        :key="index"
        :index="index"
        @delete="handleDelete"
      ></todo-item>
    </ul>
    <router-view />
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem";
export default {
  name: "App",
  components: {
    "todo-item": TodoItem
  },
  data: function() {
    return {
      inputValue: "",
      list: []
    };
  },
  methods: {
    handleSubmit: function() {
      if (this.inputValue.trim() != "") {
        this.list.push(this.inputValue);
        this.inputValue = "";
      }
    },
    handleDelete: function(index) {
      this.list.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
