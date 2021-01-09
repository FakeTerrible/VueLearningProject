<template>
  <div id="Plan">
    <div class="prepare">
      <div class="left">{{ checkedGoods }}</div>
      <div class="right">{{ plan }}</div>
    </div>

    <div class="input-area">
      <div class="left">
        <input
          type="checkbox"
          id="xiangchang"
          value="跑步"
          v-model="checkedGoods"
        />
        <label for="xiangchang">跑步</label>
        <input
          type="checkbox"
          id="fengzhua"
          value="仰卧起坐"
          v-model="checkedGoods"
        />
        <label for="fengzhua">仰卧起坐</label>
        <input type="checkbox" id="yujia" value="瑜伽" v-model="checkedGoods" />
        <label for="yujia">瑜伽</label>
      </div>
      <div class="right">
        <textarea placeholder="请输入你的健身计划" v-model="plan"></textarea>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Plan",
  data() {
    return {
      checkedGoods: [],
      plan: "",
    };
  },
};
</script>

<style scoped>
.prepare {
  display: flex;
  width: 500px;
  min-height: 100px;
  border: 1px solid black;
}

.prepare .left {
  flex: none;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 150px;
  background: #c8c8a9;
}

.prepare .right {
  flex: 1;
  background: #83af9b;
}

.input-area {
  margin-top: 10px;
  width: 500px;
  height: 100px;
  display: flex;
  border-radius: 5px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.11);
}

.input-area .right {
  flex: 1;
  margin-left: 10px;
}

.input-area .right textarea {
  box-sizing: border-box;
  overflow: hidden;
  width: 100%;
  height: 100%;
  border: none;
  resize: none;
  outline: none;
  padding: 5px;
}
</style>