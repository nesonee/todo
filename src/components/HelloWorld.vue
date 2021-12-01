<script lang="ts">
import {defineComponent} from "vue";
import Item from "./Item.vue";

export default defineComponent({
  name: "HelloWorld",
  components: {Item},
  data() {
    return {
      inputText: "",
      todos: new Map(),
      index: 0
    }
  },
  methods: {
    showText: function () {
      if (this.inputText == "") {
        return
      }
      this.todos.set(this.index++, this.inputText)
      console.log(this.todos)
    },
    onClickDeal: function (key) {
      this.todos.delete(key)
      console.log("del")
    }
  }
})
</script>

<template>
  <div class="todos_box">
    <input class="tb_input" v-model="inputText" placeholder="todo...">
    <div class="tb_btn" @click="showText">点击</div>
    <Item v-for="(value) in todos" :todo="value[1]" :index="value[0]" :deal="onClickDeal"></Item>
  </div>
</template>

<style scoped>
.todos_box {
  width: 520px;
  height: 50px;
  margin: 0 auto;
  text-align: left;
}

.tb_input {
  width: 400px;
  height: 50px;
  font-size: 21px;
  box-sizing: border-box;
}

.tb_btn {
  width: 80px;
  height: 50px;
  box-sizing: border-box;
  margin-left: 10px;
  cursor: pointer;
  background-color: cornflowerblue;
  float: right;
  text-align: center;
  line-height: 50px;
  font-size: 21px;
  color: white;
  border-radius: 5px;
}
</style>
