<template>
  <div class="card-container">
    <div class="func-image-wrapper full">
      <div class="func-image"></div>
    </div>
    <div class="card-image full"></div>
    <div class="card-info flex-h full">
      <div class="intel-type-wrapper flex-w">
        <span class="intel-type">Express</span>
      </div>
      <div class="empty-wrapper"></div>
      <div class="func-name-wrapper extend flex-cc">
        <p class="func-name flex-w">
          <span class="func-title">試探</span>
          <span class="func-subtitle">-1</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
@Component
export default class extends Vue {}
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css?family=Roboto+Mono&display=swap");
@import url("https://fonts.googleapis.com/css?family=Black+Ops+One&display=swap");

.full {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
}

.card-container {
  height: 140px;
  width: 105px;
  border: solid 1px white;
  margin-right: 1rem;
  border-radius: 8px;
  position: relative;
  overflow: hidden;

  .func-image-wrapper {
    .func-image {
      position: absolute;
      left: 5.5%;
      right: 5.5%;
      top: 20%;
      bottom: 33%;
      background-image: url("~@/assets/images/burn.png");
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center center;
    }
  }

  .card-image {
    background-image: url("~@/assets/images/bg-fake-card.png");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
    z-index: 1;
  }

  .card-info {
    margin: 4px 6px;
    z-index: 2;
    .intel-type-wrapper {
      justify-content: flex-end;
      align-items: center;
      height: 17%;
      padding-right: 4%;
      .intel-type {
        color: white;
        font-size: 10pt;
        font-family: "Black Ops One", cursive;
      }
    }
    .empty-wrapper {
      flex-grow: 1;
    }
    .func-name-wrapper {
      height: 33%;

      .func-name {
        align-items: flex-end;
        font-size: 14pt;

        .func-title {
          color: white;
        }
        .func-subtitle {
          font-size: 0.8em;
          color: aquamarine;
          font-family: "Roboto Mono", monospace;
          position: relative;
          bottom: 2px;
          margin-left: 0.25em;
        }
      }
    }
  }
}
</style>
