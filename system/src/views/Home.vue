<script setup>
import {reactive, ref} from "vue";

  const a = ref(77)
  const b = ref("December 23th")

  const data = reactive({
    a: 123,
    b: "Every moment is a new beginning."
  })
</script>

<template>
  <div>
    <div style="background-color: red">
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

    <div>
      <span style="color: red">小猪佩奇</span>
      <span style="color: blue">小猪乔治</span>
    </div>
  </div>

</template>
