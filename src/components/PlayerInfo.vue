<template lang="html">
  <div class="container">
    <div class="photo" style='float:left'>
      <img v-if="player.strCutout" :src=player.strCutout :alt=player.strPlayer>
    </div>
    <div class="information" style='float:right'>
      <table v-if="player">
        <tr>
          <td colspan="2" class="player-name">{{ player.strPlayer }}</td>
          <td v-if="player.strNumber" rowspan="2" class="number">{{ player.strNumber }}</td>
          <td v-else>99</td>
        </tr>
        <tr>
          <td colspan="2" class="player-positon">{{ player.strPosition }}</td>
        </tr>
        <tr>
          <td>Date of Birth:</td>
          <td class="detail">{{ player.dateBorn }}</td>
        </tr>
        <tr>
          <td>Nationality:</td>
          <td class="detail">{{ player.strNationality }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'player-info',
  props: ['player']
}
</script>

<style lang="css" scoped>

.container {
  flex: auto;
  width: 80%;
}

td, th {
  width: 200px;
  font-family: antique-olive, sans-serif;
  font-weight: 400;
  color: white;
}
img {
  width: 250px;
}
.player-name{
  font-size: 26px;
  background-color: #9C824A;
  margin-bottom: 0px;
}
.player-position{
  font-size: 16px;
  background-color: #9C824A;
  padding: 0px;
  margin: 0px;
}
.detail{

}
.number{
  font-size: 100px;
  text-align: center;
  padding: 0px;
  margin: 0px;
}
</style>
