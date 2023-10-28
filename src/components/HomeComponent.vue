<template>
  <div class="home">
    <h1>HOME</h1>
    <SongListComponent></SongListComponent>
  </div>
</template>

<script>
</script>

<style>
#body {
  display: grid;
  grid-template-columns: 396px auto;
  height: 100vh;
}

.home {
  height: 100%;
  background: #191621;
}

.home h1 {
  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
  margin: 0;
  margin-left: 40px;
  margin-top: 30px;
}

table {
  width: 100%;
  font-family: monospace;
  font-size: 25px;
  text-align: left;
}

thead tr th {
  color: #464157;
  background-color: #191621;
  border: none;
  border-bottom: 1px solid #464157;
}

tbody tr td {
  border: none;
  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
}
</style>