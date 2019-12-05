<template>
  <div class="myClass">
    <button v-on:click="count++">Vous m\'avez cliqué {{ count }} fois. (W3)</button>
  </div>
</template>

<script>
module.exports = {
  name: 'widgetCounter',
  data: function () {
    return {
      count: 0
    }
  }
}
</script>

<style scoped>
.myClass {
  background-color: blue;
  width: 200px;
  height: 40px;
}
</style>