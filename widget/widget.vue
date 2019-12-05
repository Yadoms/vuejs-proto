<template>
  <div class="myClass">
    <button v-on:click="count++">Vous m'avez cliqué {{ count }} fois. (W1)</button>
    <div class="myLogo"></div>
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
  background-color: red;
  width: 200px;
  height: 40px;
}
.myLogo {
  background-color: red;
  background-image:url(./public/logo.png);
  background-repeat: no-repeat;
  background-size: contain;
  width: 48px;
  height: 48px;
}
</style>