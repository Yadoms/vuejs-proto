<template>
  <div class="App">
        <header class="header">Movies of 2018 (Vue)</header>
        <button v-on:click="greet">load</button>

        <component v-bind:is="componentName1"></component>
        <component v-bind:is="componentName2"></component>
        <component v-bind:is="componentName3"></component>
  </div>

</template>

<script>
import externalComponent from './utils/widget-loader';
import Vue from 'vue'

var AsyncComponent = () => ({
  // Le composant à charger (doit être une `Promise`)
  component: externalComponent(AsyncComponent.url),
  // Un composant à utiliser pendant que le composant asynchrone se charge
  loading: ()=>{},
  // Un composant d'erreur à utiliser au cas où le chargement échoue
  error: ()=>{},
  // Le délai à patienter avant d'afficher le composant de chargement. Par défaut : 200ms.
  delay: 200,
  // Le composant d'erreur sera affiché si un délai de timeout est fourni et dépassé.
  // Par défaut: délai infini.
  timeout: 3000,
  url:''
})


export default {
  name: 'app',
  components: {
    AsyncComponent
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

  Vue.component(
    'w1',
    // The `import` function returns a Promise.
    () => externalComponent('widgets/widget1/widget1.umd.min.js', 'widgets/widget1/widget1.css')
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

 /*
      this.MyComponent = () => externalComponent('MyComponent.3e524a07a3b707c0ffe7.umd.min.js');

      this.MyComponent().then((aa) =>
        {
          debugger;
          this.awesome = true;
          this.componentName = aa.name;
        }
      );*/
/*
      externalComponent("MyComponent.3e524a07a3b707c0ffe7.umd.min.js")
      .then( cmpName => {
        debugger;
        this.componentName = 'widgetCounter';
      });
      */
    }
  }
}
</script>

<style>
  @import './App.css';
</style>
