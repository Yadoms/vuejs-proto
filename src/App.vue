<template>
  <div class="App">
        <header class="header">Prototype Yadoms - VUEJS plop</header>
        <button v-on:click="loadWidgets">charger widgets asynchrones</button>
        <button v-on:click="changeFoo">upateFoo</button>

        <component v-bind:is="componentName1"></component>
        <br/>
        <br/>
        <component v-bind:is="componentName2"></component>
        <br/>
        <br/>
        <component v-bind:is="componentName3"></component>
  </div>

</template>

<script>
import externalComponent from './utils/widget-loader';
import Vue from 'vue'

const apiInstance = {
  v : Vue.observable({bar: 42}),
  f : function() {
      this.v.bar*=2;
  },
  p : function(t) {
      this.v.bar += t;
  },
  
};

export default {
  name: 'app',
  components: {
  },
	data:()=>({
    componentName1:'',
    componentName2:'',
    componentName3:'',
  }),
  provide: {
    api: apiInstance,
    vue: Vue
  },
// Définissez les méthodes de l'objet
  methods: {
    changeFoo: function() {
      apiInstance.f();
    },
    loadWidgets: function () {

      Vue.component(
        'w1',
        // The `import` function returns a Promise.
        () => externalComponent('widgets/widget1/widget1.umd.min.js')
      )
      this.componentName1 = 'w1';

      Vue.component(
        'w2',
        // The `import` function returns a Promise.
        () => externalComponent('widgets/widget2/widget2.umd.min.js')
      )
      this.componentName2 = 'w2';

      Vue.component(
        'w3',
        // The `import` function returns a Promise.
        () => externalComponent('widgets/widget3/widget3.umd.min.js')
      )
      this.componentName3 = 'w3';

    }
  }
}
</script>

<style>
  @import './App.css';
</style>
