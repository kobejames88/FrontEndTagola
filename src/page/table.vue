<template>
  <div>
    <el-button @click="$refs.editable.insert({name: 'num'})">add</el-button>
    <el-button @click="$refs.editable.removeSelecteds()">delete</el-button>
    <el-button @click="$refs.editable.clear()">empty</el-button>
    <elx-editable ref="editable" :data.sync="tableData">
      <elx-editable-column type="selection" width="55"></elx-editable-column>
      <elx-editable-column type="index" width="55"></elx-editable-column>
      <elx-editable-column prop="name" label="read only"></elx-editable-column>
      <elx-editable-column prop="sex" label="sex" :edit-render="{name: 'ElSelect', options: sexList}"></elx-editable-column>
      <elx-editable-column prop="age" label="data" :edit-render="{name: 'ElInputNumber'}"></elx-editable-column>
      <elx-editable-column prop="date" label="date" :edit-render="{name: 'ElDatePicker', attrs: {type: 'date', format: 'yyyy-MM-dd'}}"></elx-editable-column>
      <elx-editable-column prop="flag" label="switch" :edit-render="{name: 'ElSwitch', type: 'visible'}"></elx-editable-column>
      <elx-editable-column prop="remark" label="text" :edit-render="{name: 'ElInput'}"></elx-editable-column>
    </elx-editable>
  </div>
</template>

<script>

import Vue from 'vue'
import VueElementExtends from 'vue-element-extends'
import 'vue-element-extends/lib/index.css'
 
Vue.use(VueElementExtends)
export default {
  data () {
    return {
      tableData: [{
        date: 1551322088449,
        name: 'Tomcat',
        sex: '1',
        age: '26',
        flag: false,
        remark: '备注'
      }],
      sexList: [
        {
          'label': '男',
          'value': '1'
        },
        {
          'label': '女',
          'value': '0'
        }
      ]
    }
  }
}
</script>