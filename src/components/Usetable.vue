<template>
  <div id="Usetable">
    <div class="list">
      <div class="title">
        <div class="name">姓名</div>
        <div class="class">班级</div>
        <div class="total-grade">总成绩</div>
      </div>
      <div class="line">
        <div class="name-data" @click="getData(0, 'name')">
          {{ list[0].name }}
        </div>
        <div class="class-data" @click="getData(0, 'grade')">
          {{ list[0].grade }}
        </div>
        <div class="total-grade-data" @click="getData(0, 'mark')">
          {{ list[0].mark }}
        </div>
      </div>
      <div class="line">
        <div class="name-data" @click="getData(1, 'name')">
          {{ list[1].name }}
        </div>
        <div class="class-data" @click="getData(1, 'grade')">
          {{ list[1].grade }}
        </div>
        <div class="total-grade-data" @click="getData(1, 'mark')">
          {{ list[1].mark }}
        </div>
      </div>
      <div class="line">
        <div class="name-data" @click="getData(2, 'name')">
          {{ list[2].name }}
        </div>
        <div class="class-data" @click="getData(2, 'grade')">
          {{ list[2].grade }}
        </div>
        <div class="total-grade-data" @click="getData(2, 'mark')">
          {{ list[2].mark }}
        </div>
      </div>
      <div class="change">
        <input
          type="text"
          v-model="changingData"
          placeholder="请输入...."
          @focus="focusFn"
        />
        <div @click="changeData" class="sub">提交</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Usetable',
  data() {
    return {
      list: [
        {
          name: '张三',
          grade: '三年级二班',
          mark: 290,
        },
        {
          name: '李四',
          grade: '三年级二班',
          mark: 270,
        },
        {
          name: '王五',
          grade: '三年级二班',
          mark: 270,
        },
      ],
      changingData: '',
      currentIndex: 0,
      currentKey: '',
    };
  },
  methods: {
    getData: function (index, key) {
      this.currentIndex = index;
      this.currentKey = key;
      this.changingData = this.list[index][key];
    },
    changeData: function () {
      if (!this.changingData) {
        console.log('请选择要更改的表格');
      }
      this.list[this.currentIndex][this.currentKey] = this.changingData;
      console.log(this.list);
    },
    focusFn: function () {
      if (!this.changingData) {
        console.log('请选择要更改的表格');
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.list {
  width: 500px;
  background: #34405a;
  color: #ffffff;
  .title {
    display: flex;
    padding: 5px 0;
    background: #36507e;
    div {
      flex: 1;
    }
  }
  .line {
    padding: 5px 0;
    background: #222c44;
    display: flex;
    border-bottom: 1px solid #020b1a;
    div {
      flex: 1;
    }
  }
  .change {
    display: flex;
    padding: 5px 0;
    input {
      border: none;
      background: transparent;
      margin-right: 20px;
      outline: 0;
      color: #ffffff;
      padding: 5px 20px;
    }
    .sub {
      cursor: pointer;
    }
  }
}
</style>

