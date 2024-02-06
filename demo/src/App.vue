<script setup>
import { ref } from 'vue'

// const props = defineProps({
//   bordered: { type: Boolean, default: true }
// })
//
// let borderedValue = ref(props.bordered)
// borderedValue.value = props.bordered

let borderedValue = ref(true)

const data = {
  dataSource: [],
  columns: [
    {
      title: '姓名',
      dataIndex: 'name',
      key: 'name',
    },
    {
      title: '年龄',
      dataIndex: 'age',
      key: 'age',
    },
    {
      title: '住址',
      dataIndex: 'address',
      key: 'address',
    },
  ],
}
for (let i = 0; i < 10; i++) {
  data.dataSource.push({
    key: `${i}`,
    name: `姓名${i}`,
    age: i,
    address: '西湖区湖底公园1号',
  });
}

</script>

<template>
  <div >
    边框显示：<a-switch v-model:checked="borderedValue" checked-children="开" un-checked-children="关" />
    <br /><br />
    <a-table :bordered="borderedValue" :dataSource="data.dataSource" :columns="data.columns" />
  </div>

</template>

<style scoped>
</style>
