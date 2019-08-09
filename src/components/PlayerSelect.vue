<template lang="html">
    <select @change="playerSelected" class="custom-select">
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
select {
  display: block;
  margin: 0 auto;
}
.custom-select {
  font-family: antique-olive-nord, sans-serif;
  font-weight: 400;
  font-size: 18px;
  color: white;
  background-color: black;
  width: 40%;
  height: 40px;
}
</style>
