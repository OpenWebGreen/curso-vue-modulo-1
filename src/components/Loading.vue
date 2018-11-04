<template>
  <img ref='image' v-if='show' src="../assets/loading.gif" />
</template>

<script>
export default {
  data() {
    return{
      show: false
    }
  },
  beforeCreate () {
    console.log('beforeCreate')
  },
  created() {
    console.log('created')
  },
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    this.show = true
    console.log('mounted')
  },
  beforeUpdate() {
    console.log('beforeUpdate')
  },
  updated() {
    console.log('updated')
  },
  beforeDestroy() {
    console.log('beforeDestroy')
  },
  destroyed() {
    console.log('destroyed')
  }
}
</script>
