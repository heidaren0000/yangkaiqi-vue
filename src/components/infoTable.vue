<template>
  <div>
  <table style="width:100%">
    <tr>
      <th v-for="header in headers" :key="header" >{{ header }}</th>
    </tr>
    <tr v-for="record in info" :key="record.id">
      <td>{{ record.id }}</td>
      <td>{{ record.title }}</td>
      <td>{{ record.price_info }}</td>
      <td>{{ record.is_show }}</td>
      <td><button type="button" @click="delete_record(record)">删除</button></td>
    </tr>
  </table>
  </div>
</template>

<script>
export default {
  name: 'infoTable',
  props: {
    info: Array,
    headers: Array
  },
  methods: {
    delete_record(record) {
      this.$emit('delete', record);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
</style>
