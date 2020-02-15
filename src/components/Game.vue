<template></template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import Player from "@/components/Player.vue";

@Component({ components: { Player } })
export default class extends Vue {}
</script>