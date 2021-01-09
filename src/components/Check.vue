<template>
  <div id="Check">
    <div class="list">
      <div class="title">炸鸡汉堡</div>
      <div class="food">
        <div class="check-box">
          <input type="checkbox" value="吮指原味鸡" v-model="checkedGoods" />
        </div>
        <div class="food-name">吮指原味鸡</div>
        <div class="food-price">￥11.5</div>
      </div>
      <div class="food">
        <div class="check-box">
          <input
            type="checkbox"
            value="榴莲芝士鸡腿堡"
            v-model="checkedGoods"
          />
        </div>
        <div class="food-name">榴莲芝士鸡腿堡</div>
        <div class="food-price">￥24</div>
      </div>
      <div class="food">
        <div class="check-box">
          <input
            type="checkbox"
            value="新奥尔良鸡腿堡"
            v-model="checkedGoods"
          />
        </div>
        <div class="food-name">新奥尔良鸡腿堡</div>
        <div class="food-price">￥24</div>
      </div>
      <div class="food">
        <div class="check-box">
          <input type="checkbox" value="香辣鸡腿堡" v-model="checkedGoods" />
        </div>
        <div class="food-name">香辣鸡腿堡</div>
        <div class="food-price">￥18</div>
      </div>
      <div class="title choosed">已选择</div>
      <div class="have-choosed">{{ checkedGoods }}</div>
      <div class="the-price">
        <span>{{ price }} 元</span>
        <button v-on:click="calculate" class="calculate">总计</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Check",
  data() {
    return {
      checkedGoods: [],
      price: 0
    };
  },
  methods: {
    calculate: function(){
      this.price = 0;
      const prices = {'吮指原味鸡':11.5,'榴莲芝士鸡腿堡':24,'新奥尔良鸡腿堡':24,'香辣鸡腿堡':18};
      if(this.checkedGoods.length !== 0){
        for(let i = 0; i < this.checkedGoods.length; i++){
          console.log(prices[this.checkedGoods[i]]);
          this.price += prices[this.checkedGoods[i]];
        }
      }
    }
  },
};
</script>

<style lang="scss" scoped>
.list {
  margin-bottom: 20px;
  width: 350px;
  background: #fbbf2e;
  .title {
    background: #7b573f;
    color: #fffde7;
    font-size: 22px;
    padding: 5px;
  }
  .food {
    display: flex;
    padding: 5px 10px;
    height: fit-content;
    color: #6a1818;
    font-size: 15px;
    .check-box {
      flex: none;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .food-name {
      flex: 1;
      padding-left: 20px;
      text-align: left;
    }
    .food-price {
      flex: 1;
      text-align: right;
      padding-right: 10px;
    }
  }
  .choosed {
    text-align: left;
    font-size: 18px;
    padding: 5px 20px;
  }
  .have-choosed {
    text-align: left;
    padding: 5px 20px;
  }
  .the-price{
    display: flex;
    justify-content: space-around;

    .calculate{
      color:white;
      background-color: #7b573f;
      border: 1px solid #7b7b7b;
    }
  }
}
</style>