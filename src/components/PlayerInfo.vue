<template lang="html">
<div>

<table v-if="player">
  <tr>
    <td colspan="2">{{ player.strPlayer }}</td>
    <td>{{ player.strNumber }}</td>
  </tr>
  <tr>
    <td>Date of Birth:</td>
    <td>{{ player.dateBorn }}</td>
  </tr>
  <tr>
    <td>Nationality:</td>
    <td>{{ player.strNationality }}</td>
  </tr>
</table>

</div>
</template>

<script>
export default {
  name: 'player-info',
  props: ['player']
}
</script>

<style lang="css" scoped>
td, th {
  border: 1px solid #dddddd;
  width: 200px;
}
</style>
