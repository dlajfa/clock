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

  <div class="time">
    <span>{{ hours }}</span>
    <span class="separator">:</span>
    <span>{{ minutes }}</span>
    <span class="separator large-screen-only">:</span>
    <span class="large-screen-only">{{ seconds }}</span>
  </div>

</template>



<style>

  div.time {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20vw;
    font-weight: 900;
    font-family: Helvetica, sans-serif;
  }

  span.separator {
    position: relative;
    bottom: 1.5vw;
  }

  @media screen and (max-width: 600px) {
    #app {
      margin-bottom: 50%;
    }

    div.time {
      font-size: 30vw;
    }

    span.large-screen-only {
      display: none;
    }
  }

</style>