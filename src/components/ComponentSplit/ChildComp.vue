<template>
  <div>
    {{heavy()}}
  </div>
</template>

<script>
export default {
  setup(props) {
    const heavy = () => {
      let count = 0
      for(let i = 0; i < 10000; i++) {
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