<template lang="html">
  <select>
    <option disabled option selected='selected'>Select Player</option>
    <option v-for="(player, index) in players">{{ player.strPlayer }}</option>
  </select>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'player-select',
  props: ['players']
}
</script>

<style lang="css" scoped>
</style>
