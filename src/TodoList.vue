<template>
  <div>
    <div>
      <input type="text" v-model="inputValue" />
      <button @click="handleSumbit">提交</button>
    </div>
    <ul>
      <todo-item
        v-for="(item,index) of list"
        :key="index"
        :content="item"
        :index="index"
        @delete="handleDelete"
      ></todo-item>
    </ul>
  </div>
</template>

<script>
  import TodoItem from "./components/TodoItem";
  export default {
    components: {
      "todo-item": TodoItem
    },
    data() {
      return {
        inputValue: "",
        list: []
      };
    },
    methods: {
      handleSumbit: function() {
        this.list.push(this.inputValue);
        this.inputValue = "";
      },
      handleDelete: function(index) {
        this.list.splice(index, 1);
      }
    }
  };
</script>

<style></style>
