<template lang="html">
  <select @change="playerSelected">
    <option disabled option selected='selected'>Select Player</option>
    <option v-for="(player, index) in players" :value="index">{{ player.strPlayer }}</option>
  </select>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'player-select',
  props: ['players'],
  methods: {
    playerSelected(e) {
      const selectedIndex = e.target.value;
      eventBus.$emit('player-selected', selectedIndex);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
