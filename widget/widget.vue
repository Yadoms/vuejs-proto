<template>
  <div class="myClass">
    <button v-on:click="count++">Vous m'avez cliqué {{ count }} fois. Foo={{api.v}} (W1)</button>
    <button v-on:click="api.f()">x2</button>
    <button v-on:click="api.p(5)">+5</button>
    <div class="myLogo"></div>
  </div>
</template>

<script>
module.exports = {
  name: 'widgetCounter',
  inject: ['api'],
  data: function () {
    return {
      count: 0
    }
  },
  created () {
    console.log(this.api.v) // => "bar"
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