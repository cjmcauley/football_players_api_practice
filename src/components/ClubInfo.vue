<template lang="html">
  <div v-if="club" class="club-info">
    <div class="club-name">

      <h1><a href="http://localhost:8080/" class="header-link">{{ club.strTeam }}</a></h1>
    </div>
    <div class="logo-div">

      <img class="logo" :src=club.strTeamBadge :alt=club.strTeam>
    </div>
  </div>
</template>

<script>

  export default {
    name: 'club-info',
    props: ['club']
  }
</script>

<style lang="css" scoped>
.logo{
  max-width:100%;
  height:auto;
}
.club-info{
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0px 25px;
  margin: 0px;
}
.logo-div{
  width: 10%;
}
.header-link{
  color: white;
  text-decoration: none;
}
</style>
