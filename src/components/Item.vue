<template>
  <div class="item_box">
    <div class="ib_show">{{ todo }}</div>
    <svg class="ib_deal icon" aria-hidden="true" @click="deal(index)">
      <use xlink:href="#icon-tijiao1"></use>
    </svg>

  </div>
</template>

<script lang="ts">
import {defineComponent, inject} from "vue";

export default defineComponent({
  name: "Item",
  props: {
    todo: String,
    index: Number,
    deal: Function
  }
})
</script>

<style scoped>
.item_box {
  display: flex;
  justify-content: space-between;
  height: 50px;
  font-size: 21px;
  background-color: #ccffcc;
  padding: 0 10px;
  border-radius: 5px;
  margin: 5px 0;
}

.ib_show {
  line-height: 50px;
}

.ib_deal {
  width: 30px;
  height: 50px;
  color: gray;
  line-height: 50px;
  cursor: pointer;
}
.ib_deal:hover{
  color: lightskyblue;
}
</style>
