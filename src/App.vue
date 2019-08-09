<template lang="html">
<h1>Players</h1>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      players: []
    };
  },
  mounted(){
    fetch('https://www.thesportsdb.com/api/v1/json/1/searchplayers.php?t=Arsenal')
    .then(result => result.json())
    .then(players => this.players = players)
  }
}
</script>

<style lang="css" scoped>
</style>
