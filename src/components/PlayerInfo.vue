<template lang="html">
  <div class="container">
    <div class="photo" style='float:left'>
      <img v-if="player && player.strCutout" :src=player.strCutout :alt=player.strPlayer>
    </div>
    <div class="information" style='float:right'>
      <table v-if="player">
        <tr>
          <td colspan="2" class="player-name">{{ player.strPlayer }}</td>
          <td v-if="player.strNumber" rowspan="2" class="number">{{ player.strNumber }}</td>
          <td v-else rowspan="2" class="number">99</td>
        </tr>
        <tr>
          <td colspan="2" class="player-position" valign="top">{{ player.strPosition }}</td>
        </tr>
        <tr>
          <td>Date of Birth</td>
          <td class="detail">{{ player.dateBorn }}</td>
        </tr>
        <tr>
          <td>Nationality</td>
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
  display: flex;
  justify-content: space-around;
}
table{
  border-collapse: collapse;
}
td, th {
  width: 200px;
  font-family: antique-olive, sans-serif;
  font-weight: 400;
  font-size: 26px;
  padding: 0px 25px;
  background: #469FB9;
  margin: 15px;
  color: white;
}
img {
  width: 250px;
}
.player-name{
  font-family: antique-olive-nord, sans-serif;
  font-weight: 400;
  font-size: 56px;
  background-color: #F6C30A;
  margin-bottom: 0px;
}
.player-position{
  font-family: antique-olive-nord, sans-serif;
  font-weight: 400;
  font-style: italic;
  font-size: 26px;
  background-color: #F6C30A;
  margin: 0px;
  font-style: italic;
}
.detail{

}
.number{
  font-family: antique-olive-nord, sans-serif;
  width: 150px;
  font-size: 120px;
  text-align: center;
  color: white;
  background: #EE4808;
}
.photo{
  padding-left: 40px;
  margin: 0px;
}
</style>
