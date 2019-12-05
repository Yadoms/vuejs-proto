<template>
  <div class="myClass">
    <button v-on:click="count++">Vous m\'avez cliqué {{ count }} fois. (W2)</button>
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
  background-color: green;
  width: 200px;
  height: 40px;
}
</style>