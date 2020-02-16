<template>
  <div id="game-view" class="flex-w">
    <div class="left-seat-container seat-container flex-h">
      <div class="player-wrapper">
        <Player class="player-view" />
        <div class="intel-loc"></div>
      </div>
      <div class="player-wrapper">
        <Player class="player-view" />
        <div class="intel-loc"></div>
      </div>
      <div class="player-wrapper me">
        <Player class="player-view" />
      </div>
    </div>
    <div class="flex-h expand">
      <div class="flex-w ww expand">
        <div class="flex-h expand">
          <div class="top-seat-container seat-container flex-w ww">
            <div class="player-wrapper">
              <Player class="player-view" />
              <div class="intel-loc"></div>
            </div>
            <div class="player-wrapper">
              <Player class="player-view" />
              <div class="intel-loc"></div>
            </div>
            <div class="player-wrapper">
              <Player class="player-view" />
              <div class="intel-loc"></div>
            </div>
            <div class="player-wrapper">
              <Player class="player-view" />
              <div class="intel-loc"></div>
            </div>
          </div>
          <div class="ww expand" style="padding: 30px">
            <div class="game-table wwhh"></div>
          </div>
        </div>
        <div class="right-seat-container seat-container flex-h">
          <div class="player-wrapper">
            <Player class="player-view" />
            <div class="intel-loc"></div>
          </div>
          <div class="player-wrapper">
            <Player class="player-view" />
            <div class="intel-loc"></div>
          </div>
        </div>
      </div>
      <div class="my-view flex-w ww">
        <div class="hand-container flex-w">
          <GameCard class="game-card hand" />
          <GameCard class="game-card hand" />
          <GameCard class="game-card hand" />
          <GameCard class="game-card hand" />
        </div>
        <div class="control-panel"></div>
      </div>
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

<style lang="scss">
#game-view {
  $player-view-space: 1rem;

  .top-seat-container {
    justify-content: center;
    .player-wrapper {
      display: flex;
      flex-direction: column;
      align-items: center;
      &:not(:first-child) {
        margin-left: $player-view-space;
      }
    }
  }

  .left-seat-container {
    justify-content: flex-end;
    .player-wrapper {
      display: flex;
      flex-direction: row;
      align-items: center;
      margin-bottom: $player-view-space;
      &.me {
        margin-bottom: 0;
        .time-bar {
          display: none;
        }
      }
    }
  }

  .right-seat-container {
    justify-content: flex-end;
    .player-wrapper {
      display: flex;
      flex-direction: row-reverse;
      align-items: center;
      margin-bottom: $player-view-space;
    }
  }

  .intel-loc {
    border: 1px solid lightgrey;
    width: 75px;
    height: 100px;
    margin: 15px;
  }

  .game-table {
    border: 1px solid lightgrey;
    border-radius: 28px;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.25);
    background-color: MintCream;
  }

  .my-view {
    margin-top: 15px;
    margin-left: -104px;
    width: calc(100% + 104px);
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
