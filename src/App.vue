<template lang="html">
<div >
  <h1>Players</h1>
    <player-select :players="players" />
  </div>
</template>

<script>
import { eventBus } from './main.js';
import PlayerSelect from './components/PlayerSelect.vue'

export default {
  name: 'app',
  components: {
    'player-select': PlayerSelect
  },
  data() {
    return {
      players: []
    };
  },
  mounted(){
    fetch('https://www.thesportsdb.com/api/v1/json/1/searchplayers.php?t=Arsenal')
    .then(result => result.json())
    .then(players => players = players.player)
    .then(players => this.players = players)
  }
}
</script>

<style lang="css" scoped>
</style>
