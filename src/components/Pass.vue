<template>
  <div id="Pass">
    <p>是否通过考试：{{score!==''?isPassed() ? '恭喜你，通过了本次考试～':'很遗憾，你没有通过考试':''}}</p>
    <input type="text" v-model="score" placeholder="请输入你的成绩..." />
  </div>
</template>

<script>
export default {
  name: "Pass",
  // 数据
  data() {
    return {
      score: ""
    };
  },
  methods: {
    isPassed() {
      return parseInt(this.score) >= 60;
    }
  }
};
</script>

<style scoped>
input {
  width: 200px;
  height: 30px;
  font-size: 16px;
  padding: 0 10px;
  outline: none;
  border: none;
  border-radius: 5px;
}
</style>