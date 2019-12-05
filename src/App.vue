<template>
  <div class="App">
        <header class="header">Prototype Yadoms - VUEJS</header>
        <button v-on:click="greet">charger widgets asynchrones</button>

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

export default {
  name: 'app',
  components: {
  },
	data:()=>({
    componentName:'',
    componentName1:'',
    componentName2:'',
    componentName3:'',
    awesome:null
	}),  
// Définissez les méthodes de l'objet
  methods: {
    greet: function () {
      this.awesome = true;

      var api : {
        value: 42;
      };

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
