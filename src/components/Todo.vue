<template>
  <div class="block_todo">
    <div class="list">
      <h2>{{ operate.task }}</h2>
      <h3>{{ operate.time }}</h3>
    </div>
    <img :src="operate.del_icon" @click="deleteItem(operate)" />
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["operate"],
  methods: {
    deleteItem: function (operate) {
      this.$emit("deleted", operate);
    },
  },
};
</script>

<style>
.wrapper {
  font-family: "Gilroy";
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 300px));
  grid-gap: 20px;
  grid-row-gap: 10px;
  padding: 0 35px;
}
.block_todo {
  overflow: hidden;
  padding: 20px;
  margin-top: 10px;
  height: 130px;
  background: #f0f0f0;
  border: 1.5px solid #007fff;
  box-sizing: border-box;
  border-radius: 10px;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  transition: 0.3s ease;
  position: relative;
}
.block_todo:hover{
  transform: scale(1.05);
}
.list {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  height: 100%;
  grid-gap: 30px;
}
.list h2 {
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
}
.list h3 {
  font-style: italic;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: rgba(0, 0, 0, 0.55);
}
.block_todo img {
  cursor: pointer;
  width: 20px;
  height: 20px;
  transition: 0.3s ease;
}
.block_todo img:hover{
  color: red;
  transform: scale(1.15);
}
</style>