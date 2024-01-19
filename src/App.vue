<script setup>

  import { ref, computed } from 'vue'

  // 获取当前时间
  const time = ref(new Date)

  // 每隔1秒重新获取当前时间
  setInterval(() => {
    time.value = new Date()
  }, 1000)

  // 获取小时数
  const hours = computed(() => {
    return String(time.value.getHours()).padStart(2, '0')
  })

  // 获取分钟数
  const minutes = computed(() => {
    return String(time.value.getMinutes()).padStart(2, '0')
  })

  // 获取秒数
  const seconds = computed(() => {
    return String(time.value.getSeconds()).padStart(2, '0')
  })

</script>



<template>

  <div>
    {{ hours }}:{{ minutes }}:{{ seconds }}
  </div>

</template>



<style>

  div {
    font-size: 20vw;
    font-weight: 900;
    font-family: clock, monospace;
  }

</style>