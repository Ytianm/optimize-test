<template>
  <div>
    <!-- 优化前 -->
    <!-- {{ heavy() }} -->

    <!-- 优化后 -->
    <ChildComp />
  </div>
</template>

<script>
import { h } from 'vue'
// import ChildComp from './ChildComp.vue'
export default {
  components: {
    ChildComp: {
      methods: {
        heavy () {
          let count = 0
          for (let i = 0; i < 10000; i++) {
            count += Math.sqrt(Math.cos(Math.sin(30)))
          }
          return count
        }
      },
      render() {
        return h('div', this.heavy())
      }
    }
  },
  setup (props) {
    const heavy = () => {
      let count = 0
      for (let i = 0; i < 10000; i++) {
        count += Math.sqrt(Math.cos(30))
      }
      return count
    }

    return {
      heavy
    }
  }
}
</script>

<style>
</style>