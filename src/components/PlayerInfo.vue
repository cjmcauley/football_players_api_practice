<template lang="html">
  <div v-if="player" class="container">
    <div class="photo" style='float:left'>
      <img v-if="player && player.strCutout" :src=player.strCutout :alt=player.strPlayer>
    </div>
    <div class="information" style='float:right'>
      <table >
        <tr>
          <td colspan="2" class="player-name">{{ player.strPlayer }}</td>
          <td v-if="player.strNumber" rowspan="2" class="number">{{ player.strNumber }}</td>
          <td v-else rowspan="2" class="number">99</td>
        </tr>
        <tr>
          <td colspan="2" class="player-position" valign="top">{{ player.strPosition }}</td>
        </tr>
        <tr>
          <td class="detail">Date of Birth</td>
          <td class="detail">{{ player.dateBorn }}</td>
        </tr>
        <tr>
          <td class="detail">Nationality</td>
          <td class="detail">{{ player.strNationality }}</td>
        </tr>
      </table>
    </div>
  </div>
  <div v-else>
    <h1 class="sub-header" align="center">First Team Squad 2019/20</h1>
    <img class="team" src="https://i0.wp.com/arsenaltruefans.com/wp-content/uploads/2018/09/IMG_20180918_185336_123.jpg?w=910&ssl=1" alt="">
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
  background: #F6C30A;
  margin: 15px;
  color: black;
}
img {
  width: 250px;
}
.team {
  display: block;
  width: 60%;
  margin: auto;
  border: 3px solid #F6C30A;
}
.sub-header{
  font-size: 26px;
  width: 60%;
  color: black;
  background-color: #F6C30A;
  padding: 5px;
  margin: auto;
  margin-bottom: 10px;
}
.player-name{
  font-family: antique-olive-nord, sans-serif;
  font-weight: 400;
  font-size: 56px;
  background-color: #F6C30A;
  margin-bottom: 0px;
  padding: 0px 25px;
}
.player-position{
  font-family: antique-olive-nord, sans-serif;
  font-weight: 400;
  font-style: italic;
  font-size: 26px;
  background-color: #F6C30A;
  margin: 0px;
  font-style: italic;
  border-bottom: 2px solid black;
  padding-bottom: 15px;
}
.detail{
  padding: 5px 25px;
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
