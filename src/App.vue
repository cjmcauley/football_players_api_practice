<template lang="html">
  <div>
    <header>
      <club-info :club="club[0]" />
  </header>
      <hr>
    <player-select :players="players" />
    <hr>
    <player-info :player="selectedPlayer" />
  </div>
</template>

<script>
import { eventBus } from './main.js';
import PlayerSelect from './components/PlayerSelect.vue'
import PlayerInfo from './components/PlayerInfo.vue'
import ClubInfo from './components/ClubInfo.vue'

export default {
  name: 'app',
  components: {
    'player-select': PlayerSelect,
    'player-info': PlayerInfo,
    'club-info': ClubInfo
  },
  data() {
    return {
      players: [],
      selectedPlayer: null,
      club: []
    };
  },
  mounted(){
    eventBus.$on('player-selected', (selectedIndex) => {
      this.selectedPlayer = this.players[selectedIndex];
    })
    fetch('https://www.thesportsdb.com/api/v1/json/1/searchplayers.php?t=Arsenal')
    .then(result => result.json())
    .then(players => players = players.player)
    .then(players => this.players = players),
    fetch('https://www.thesportsdb.com/api/v1/json/1/lookupteam.php?id=133604')
    .then(result => result.json())
    .then(team => team = team.teams)
    .then(club => this.club = club)
  }
}
</script>

<style lang="css">
hr{
  border: 1px solid black;
}
h1 {
  font-family: antique-olive-nord, sans-serif;
  font-weight: 400;
  font-style: italic;
  font-size: 66px;
  background-color: black;
  color: white;
}
header{
  background-color: black;
}
</style>
