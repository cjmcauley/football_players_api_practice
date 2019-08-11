<template lang="html">
  <div class="main-page">
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
            <td>{{ dateBorn }}</td>
          </tr>
          <tr>
            <td class="detail">Nationality</td>
            <td>{{ player.strNationality }}</td>
          </tr>
        </table>
      </div>
    </div>
    <div v-else>
      <h1 class="sub-header" align="center">First Team Squad 2019/20</h1>
      <img class="team" src="https://i0.wp.com/arsenaltruefans.com/wp-content/uploads/2018/09/IMG_20180918_185336_123.jpg?w=910&ssl=1" alt="">
    </div>
    <div class="about" v-if="player">
      <h3 v-if="visible === true" @click="showDetails">About -</h3>
      <p v-if="visible === true">{{ player.strDescriptionEN }}</p>
      <h3 v-else="visible === false" @click="showDetails">About +</h3>
      <p v-if="visible === false"></p>
    </div>
  </div>

</template>

<script>
export default {
  name: 'player-info',
  props: ['player'],
  data() {
    return {
      visible: false
    }
  },
  computed: {
    dateBorn: function() {
      return this.player.dateBorn.split("-").reverse().join("-");
    }

  },
  methods: {
    showDetails() {
      this.visible = !this.visible;
    }
  }
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
  background: #469fb9;
  margin: 15px;
  color: white;
}
h3{
  font-family: antique-olive-nord, sans-serif;
  font-style: italic;
  font-size: 25px;
  background: #F6C30A;
  padding-left: 15px;
  width: 20%;
  color: white;
}
p {
  font-family: antique-olive, sans-serif;
  font-weight: 400;
  font-size: 18px;
  text-align: justify;
  width: 80%;
  margin: auto;
}
img {
  width: 250px;
}
.about {
  cursor: pointer;
}
.team {
  display: block;
  width: 58%;
  margin: auto;
  border: 18px solid #F6C30A;
  border-radius: 5px;
}
.sub-header{
  font-size: 26px;
  width: 60%;
  color: white;
  background-color: #469fb9;
  padding: 5px;
  margin: auto;
  margin-bottom: 10px;
  border-radius: 5px;
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
  border-bottom: 5px solid white;
  padding-bottom: 15px;
}
.detail{
  padding: 5px 25px;
  font-style: italic;
}
.number{
  font-family: antique-olive-nord, sans-serif;
  width: 150px;
  font-size: 120px;
  text-align: center;
  color: white;
  background: #EE4808;
  border-left: 5px solid white;
}
.photo{
  padding-left: 40px;
  margin: 0px;
}
</style>
