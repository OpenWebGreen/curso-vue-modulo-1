<template>
  <img v-if='inLoading' src="../assets/loading.gif" />
</template>

<script>
export default {
  props: {
    inLoading: {
      required: true,
      type: Boolean
    }
  }
}
</script>
