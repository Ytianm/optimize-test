<template>
  <div>{{ result }}</div>
</template>

<script>
import { computed } from 'vue'

export default {
  props: ['start'],
  setup (props) {
    const base = computed(() => 42)

    // // 优化前
    // const result = computed(() => {
    //   let result = props.start
    //   for (let i = 0; i < 1000; i++) {
    //     result += Math.sqrt(Math.cos(Math.sin(base.value)))
    //   }
    //   return result
    // })

    // 优化后
    const result = computed(() => {
      let result = props.start
      const b = base.value // 缓存变量，避免每次读取
      for (let i = 0; i < 1000; i++) {
        result += Math.sqrt(Math.cos(Math.sin(b)))
      }
      return result
    })

    return {
      base,
      result
    }
  }
}


</script>

<style>
</style>