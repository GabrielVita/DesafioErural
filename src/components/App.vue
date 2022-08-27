<template>
  <app-header />
  <home v-if="appState === 'idle'" :joinCall="joinCall" />
  <call
    v-else-if="appState === 'incall'"
    :leaveCall="leaveCall"
    :name="name"
    :roomUrl="roomUrl"
    :region="region"
    :size="size"
  />
</template>

<script>
import Call from "./Call.vue";
import AppHeader from "./AppHeader.vue";
import Home from "./Home.vue";

export default {
  name: "App",
  components: {
    Call,
    AppHeader,
    Home,
  },
  data() {
    return {
      appState: "idle",
      name: "Guest",
      roomUrl: null,
      region: "Guest1",
      size: null,
    };
  },
  methods: {
    /**
     * Set name and URL values entered in Home.vue form in data obj
     */
    joinCall(name, url, region, size,) {
      this.name = name;
      this.roomUrl = url;
      this.region = region;
      this.size = size;
      this.appState = "incall";
    },
    // Reset app state to return to the home screen after leaving call
    leaveCall() {
      this.appState = "idle";
    },
  },
};
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  height: 100vh;
  overflow-x: hidden;
  background-color: #121a24;
}
a {
  text-decoration: none;
  color: #2c3e50;
  display: flex;
  align-items: center;
}
body {
  margin: 0;
}
</style>
