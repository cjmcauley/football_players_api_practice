<template lang="html">
<div >
  <h1>Players</h1>
    <player-select :players="players" />
    <player-info :player="selectedPlayer" />
  </div>
</template>

<script>
import { eventBus } from './main.js';
import PlayerSelect from './components/PlayerSelect.vue'
import PlayerInfo from './components/PlayerInfo.vue'

export default {
  name: 'app',
  components: {
    'player-select': PlayerSelect,
    'player-info': PlayerInfo
  },
  data() {
    return {
      players: [],
      selectedPlayer: null
    };
  },
  mounted(){
    eventBus.$on('player-selected', (selectedIndex) => {
      this.selectedPlayer = this.players[selectedIndex];
    })
    fetch('https://www.thesportsdb.com/api/v1/json/1/searchplayers.php?t=Arsenal')
    .then(result => result.json())
    .then(players => players = players.player)
    .then(players => this.players = players)
  }
}
</script>

<style lang="css" scoped>
</style>
