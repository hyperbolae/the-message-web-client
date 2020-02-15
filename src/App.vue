<template>
  <div id="app" class="flex-w">
    <div class="main-container">
      <Game />
    </div>
    <div class="chat-container"></div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import Game from "@/components/Game.vue";

@Component({ components: { Game } })
export default class extends Vue {}
</script>

<style lang="scss">
@import "@/assets/scss/reset.scss";
@import "@/assets/scss/container.scss";

#app {
  min-height: 100vh;
  align-content: stretch;

  .main-container {
    flex-grow: 1;
  }
  .chat-container {
    width: 25%;
    max-width: 400px;
    // background: lightblue;
    box-shadow: -2px 0 2px rgba(0, 0, 0, 0.2);
  }
}
</style>
