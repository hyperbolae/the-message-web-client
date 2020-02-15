<template>
  <div class="player-view flex-h"></div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class extends Vue {}
</script>

<style lang="scss" scoped>
.player-view {
  width: 23vh;
  height: 23vh;
  border: 1px solid lightgrey;
}
</style>
