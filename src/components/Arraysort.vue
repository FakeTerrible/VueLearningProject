<template>
  <div id="Arraysort">
    <div class="tile">
      <div class="data-name">原始数据</div>
      <div class="data">{{ remoteDataStr }}</div>
    </div>
    <div class="tile">
      <div class="data-name">排序数据</div>
      <div class="data">{{ sortDataStr }}</div>
    </div>
    <div class="control">
      <input type="text" v-model="addNumber" placeholder="请输入...." />
      <div class="btn" @click="add">添加</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data: function () {
    return {
      remoteData: [],
      sortRemoteData: [],
      sortData: [],
      remoteDataStr: "",
      sortDataStr: "",
      addNumber: 0,
    };
  },
  methods: {
    add: function () {
      this.remoteData.push(this.addNumber);
      this.remoteDataStr = this.remoteData.join(",");
    },
  },
  watch: {
    remoteData: function (newData, oldData) {
      // this.sortRemoteData = this.remoteData;
      this.sortData = [];
      for (let index = 0; index < this.remoteData.length; index++) {
        const rData = this.remoteData[index];
        this.sortData.push(rData);
      }
      this.sortData.sort((a, b) => a - b);
      this.sortDataStr = this.sortData.join(",");
      console.log(newData, oldData);
    },
  },
};
</script>

<style lang="scss" scoped>
#Arraysort{
  width: 500px;
}
.tile {
  display: flex;
  color: #ffffff;
  text-align: center;
  .data-name {
    padding: 5px 0;
    background: #994d52;
    flex: 1;
  }
  .data {
    padding: 5px 0;
    background: #e6b450;
    flex: 3;
  }
}
.control {
  display: flex;
  background: #fe4365;
  padding: 5px 20px;
  input {
    color: #ffffff;
    outline: 0;
    border: none;
    background: transparent;
  }
}
</style>