<template>
<h3>{{ info }}</h3>
<h3>{{ someInfo }}</h3>

</template>

<style scoped>

</style>
<script>
export default {
  name: 'App',
  data() {
    return {
      info: 'Hello World',
      someInfo: 'This is some info'
    }
  },
  mounted() {
    console.log('App component mounted');
  }
}
</script>