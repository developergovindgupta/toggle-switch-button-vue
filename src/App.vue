<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>toggle-switch-button-vue : demo</h1>
  <br />
  <br />
  <br />
  <br />
  <div>
    <ToggleSwitchButton v-model="this.isActive" label="ON|OFF" />
  </div>
  <h1>{{ isActive }}</h1>
</template>

<script>
import ToggleSwitchButton from "./components/toggle-switch-button.vue";

export default {
  name: "App",
  components: {
    ToggleSwitchButton
  },
  data() {
    return {
      isActive: true
    };
  }
};
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
