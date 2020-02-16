<template>
  <div class="game-container flex-h ww">
    <div class="main-view flex-w ww">
      <div class="left-seat-container seat-container flex-h">
        <Player class="player-view" />
        <Player class="player-view" />
      </div>
      <div class="mid-container flex-h">
        <div class="top-seat-container seat-container flex-w ww">
          <Player class="player-view" />
          <Player class="player-view" />
          <Player class="player-view" />
          <Player class="player-view" />
        </div>
        <div class="game-table ww"></div>
        <div class="decision-button-container ww"></div>
      </div>
      <div class="right-seat-container seat-container flex-h">
        <Player class="player-view" />
        <Player class="player-view" />
      </div>
    </div>
    <div class="my-view flex-w ww">
      <Player />
      <div class="hand-container flex-w">
        <GameCard class="game-card hand" />
        <GameCard class="game-card hand" />
        <GameCard class="game-card hand" />
        <GameCard class="game-card hand" />
      </div>
      <div class="control-panel"></div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import Player from "@/components/Player.vue";
import GameCard from "@/components/GameCard.vue";

@Component({ components: { Player, GameCard } })
export default class extends Vue {}
</script>

<style lang="scss" scoped>
$player-view-margin: 1rem;

.game-container {
  height: 100%;

  .main-view {
    flex-grow: 1;

    .mid-container {
      flex-grow: 1;

      .top-seat-container {
        justify-content: center;
        .player-view:not(:first-child) {
          margin-left: $player-view-margin;
        }
      }

      .game-table {
        flex-grow: 1;
      }
    }

    .left-seat-container,
    .right-seat-container {
      justify-content: flex-end;
      .player-view {
        margin-bottom: $player-view-margin;
      }
    }
  }

  .my-view {
    box-shadow: 0 -2px 2px rgba(0, 0, 0, 0.2);

    .hand-container {
      flex-grow: 1;
      padding: 1rem;
      background: lightgoldenrodyellow;
      height: 100%;
      width: 100%;
      justify-content: flex-start;
      align-items: center;
    }
  }
}
</style>
