<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    
    <form @submit.prevent="onSubmit">
      <ValidationProvider name="E-mail" rules="required|email" v-slot="{ errors }">
        <input v-model="email" type="email">
        <span>{{ errors[0] }}</span>
      </ValidationProvider>
    <button :disabled="invalid" type="submit">Submit Here</button>

  </form>
  </div>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue';
import { ValidationProvider } from 'vee-validate';
export default {
  data: () => ({
    email: '',
  }),
  name: 'App',
  components: {
    HelloWorld,
    ValidationProvider
  },
 methods: {
    onSubmit () {
      alert('Form has been submitted!');
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
