<template>
  <div id="Count">
    <p>你点击按钮的次数是： {{ count }}</p>
    <div class="btn" @click="add">点击</div>
  </div>
</template>

<script>
export default {
  name: "Count",
  data: function () {
    return {
      count: 0,
    };
  },
  methods: {
    add: function () {
      this.count++;
    },
  },
  watch: {
    count: {
      handler: function (newCount,oldCount) {
        console.log(newCount);
        console.log(oldCount);
      },
    },
    immediate: true,
  },
};
</script>

<style lang="scss" scoped>
#Count {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.btn {
  min-width: 100px;
  background: #fe4365;
  border-radius: 25px;
  font-size: 16px;
  color: #ffffff;
  text-align: center;
  cursor: pointer;
  padding: 10px 0;
}
</style>

