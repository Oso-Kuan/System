<script setup>
import {onMounted, reactive, ref} from "vue";
import {Delete, Edit, Search, View} from "@element-plus/icons-vue";

onMounted(() =>{
  console.log('The page has loaded successfully.')

})
const a = ref(77)
const b = ref("December 23th")

const data = reactive({
  a: 123,
  b: "Every moment is a new beginning.",
  name:"佩奇",
  arr:[7,8,9],
  fruit:['apple','banana','orange'],
  language:['中文'],
  box: {
    width: '200px',
    height: '200px',
    color: '#666'
  },
  image: 'https://rusttalk.github.io/misc/xyz-qrcode.webp'
})
const click = () => {
  alert("keep it going");
}

const show = (value) => {
  alert(value)
}

const clickData = () => {
  alert('This button is form element-plus.')
}
</script>


<template>
  <div>
    <div style="background-color: darkorange">
      welcome to the home page
    </div>

    <div style="font-size: 30px; margin-bottom: 20px">
      {{a}}
      {{b}}
    </div>

    <div style="margin-bottom: 20px">
      {{data.a}}
      {{data.b}}
    </div>

    <div style="margin-bottom: 20px">
      <input v-model="data.a"/>
    </div>

    <div style="margin-bottom: 20px">
      <span style="color: red" v-if="data.name === '佩奇'">小猪佩奇</span>
      <span style="color: blue" v-else-if="data.name ==='乔治'">小猪乔治</span>
      <span style="color: aqua" v-else>Larry Page</span>
    </div>

    <div style="display: flex; ">
      <div @click="show(item)" style="width: 300px; height: 300px; background-color: aqua; text-align: center; font-size: 30px; line-height: 300px; margin-right: 30px; margin-bottom: 30px" v-for="item in data.arr">{{ item }}</div>
    </div>

    <div>
      <select style="width: 200px; margin-bottom: 20px">
        <option v-for="item in data.fruit">{{ item }}</option>
      </select>
    </div>

    <div style="margin-bottom: 20px">
      <button v-on:click="click">click me</button>
    </div>

    <div style="margin-bottom: 30px">
      <div :style="data.box"></div>
      <div>
        <img :src="data.image" alt="">
      </div>
    </div>

    <div style="margin: 30px">
      <el-button @click="clickData" :style="{color: 'green'}" >提交</el-button>
      <el-button type="primary"  size="large">确认</el-button>
      <el-button type="success" size="small" :bg="false" text>是</el-button>
      <el-button type="info" color="#626aef" style="color: red">Info</el-button>
      <el-button type="warning">Warning</el-button>
      <el-button type="danger">Danger</el-button>
    </div>

    <div style="margin-bottom: 30px">
      <el-icon :size="20">
        <Edit />
      </el-icon>

      <span style="margin-left: 30px; margin-right:30px">
        <el-icon :size="20" color="#666" style="top: 4px"><View /></el-icon> 100
      </span>

      <el-button  style="margin-right: 30px; margin-bottom: 30px" type="danger" :icon="Delete" circle />

      <el-input
          v-model="data.a"
          style="width: 240px"
          placeholder="Type something"
          :prefix-icon="Search"
      />




    </div>
  </div>


</template>
