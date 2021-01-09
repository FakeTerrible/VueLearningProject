<template>
  <div id="List">
    <table border="1">
      <tr>
        <th>商品名</th>
        <th>型号</th>
        <th>价格</th>
      </tr>
      <tr v-for="index in todoList" v-bind:key="index">
        <td>{{ index.name }}</td>
        <td>{{ index.model }}</td>
        <td>{{ index.price }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      todoList: [
        { name: "华为", model: "nava SE", price: "2199" },
        { name: "华为", model: "Mate 20", price: "3199" },
        { name: "华为", model: "畅想 10", price: "1299" },
      ],
    };
  },
};
</script>

<style scoped>
#List {
  margin-bottom: 20px;
}
table {
  border-spacing: 0px;
  color: white;
}
td {
  padding: 0 20px;
}
tr {
  background: #8d999d;
}
tr:first-child {
  background: #fd6821;
}
</style>
