<template>
  <div class="player-view flex-h">
    <div class="main-wrapper flex-h">
      <p class="id-container">
        <span class="seat">Player 1</span>
        <span class="player-id">雙曲線</span>
      </p>
      <div class="flex-w cc-wrapper">
        <div class="name-wrapper flex-h">
          <span class="cc-name latency">禮服蒙面人</span>
          <div class="team-wrapper flex-cc">
            <img src="@/assets/images/passerby.png" />
          </div>
        </div>
        <div class="intel-wrapper flex-w">
          <span class="intel red-intel flex-cc">10</span>
          <span class="intel blue-intel flex-cc">2</span>
          <span class="intel fake-intel flex-cc">2</span>
          <span class="intel hand flex-cc">10</span>
        </div>
      </div>
    </div>
    <div class="time-bar"></div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class extends Vue {}
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css?family=Noto+Serif+TC:400,700,900&display=swap");
@import url("https://fonts.googleapis.com/css?family=Revalia&display=swap");
@import url("https://fonts.googleapis.com/css?family=Noto+Sans+TC&display=swap");
@import url("https://fonts.googleapis.com/css?family=Squada+One&display=swap");

.player-view {
  .main-wrapper {
    position: relative;
    width: 220px;
    height: 240px;
    border: 1px solid lightgrey;
    border-radius: 4px;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.5);
    background-image: url("~@/assets/images/cc02.png");

    .id-container {
      font-size: 11pt;
      padding: 0.33em;
      background: rgba(0, 0, 0, 0.5);
      .seat {
        margin-right: 0.33em;
        color: yellow;
        font-family: "Squada One", cursive;
      }
      .player-id {
        color: white;
        font-family: "Noto Sans TC", sans-serif;
      }
    }

    .cc-wrapper {
      flex-grow: 1;
      padding: 0.25rem;

      .name-wrapper {
        align-items: flex-start;
        justify-content: space-between;
        .cc-name {
          font-size: 24pt;
          writing-mode: vertical-rl;
          font-family: "Noto Serif TC", Serif;
          font-weight: 900;
          letter-spacing: 0.1em;
          color: white;

          &.latency {
            text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
          }
        }

        .team-wrapper {
          // border: white solid 1px;
          border-radius: 2px;
          width: 20pt;
          height: 20pt;
          overflow: visible;
          background-color: rgba(255, 255, 255, 0.3);
          &:hover {
            background-color: rgba(255, 255, 255, 0.5);
          }

          img {
            height: 18pt;
          }
        }
      }

      .intel-wrapper {
        align-items: flex-end;
        justify-content: flex-end;
        flex-grow: 1;

        .intel {
          border-radius: 2px;
          border: white solid 1px;
          width: 20pt;
          height: 20pt;
          font-size: 12pt;
          color: white;
          font-family: "Revalia", sans-serif;
          padding-bottom: 0.4em;

          &:not(:last-child) {
            margin-right: 0.2em;
          }
          &.red-intel {
            background: rgba(255, 37, 37, 0.75);
            &:hover {
              background: rgba(255, 37, 37, 0.95);
            }
          }
          &.blue-intel {
            background: rgba(0, 114, 247, 0.75);
            &:hover {
              background: rgba(0, 144, 247, 0.95);
            }
          }
          &.fake-intel {
            background: rgba(12, 12, 12, 0.75);
            &:hover {
              background: rgba(12, 12, 12, 0.95);
            }
          }
          &.hand {
            height: 28pt;
            background: rgba(26, 119, 0, 0.75);
            &:hover {
              background: rgba(26, 119, 0, 0.95);
            }
          }
        }
      }
    }
  }

  .time-bar {
    margin-top: 3px;
    height: 6px;
    border: lightgrey solid 1px;
    border-radius: 2px;

    &.me {
      display: none;
    }
  }
}
</style>
