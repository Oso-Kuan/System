<template>
  <div>

    <div style="margin-bottom: 20px">
      <el-input v-model="data.input"  style="width: 240px" placeholder="请输入" prefix-icon="Search"></el-input> {{data.input}}
      <el-input v-model="data.input"  style="width: 240px" placeholder="请输入" suffix-icon="Calendar"></el-input>
      <el-input v-model="data.description" type="textarea" style="width:200px" placeholder="please enter the description."></el-input>
    </div>

    <el-select
        v-model="data.options"
        placeholder="Please Select"
        size="large"
        style="width: 240px"
    >
      <el-option
          v-for="item in data.options"
          :key="item"
          :label="item"
          :value="item"
      />
    </el-select>
  </div>

</template>

<script setup>
import {reactive} from "vue";
import {Search} from "@element-plus/icons-vue";

const data = reactive({
  input: null,
  description: 'dhsguifghfghdfgfdhgeth0hufghdfhfdhfdh',
  value:'',
  options: ['apple', 'banana', 'cabbage']
})
</script>