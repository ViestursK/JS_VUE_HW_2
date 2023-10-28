<template>
  <div class="landing">
    <div class="text">
      <div class="headline">
        <h1>we</h1>
        <h1 id="love">love</h1>
        <h1>music</h1>
      </div>

      <div class="powBy">
        <p>POWERED BY <span>SPOTIFY API</span></p>
      </div>

    </div>
    <div class="image">
      <img src="src\assets\backgroundImg.jfif" alt="background image">
    </div>
  </div>
</template>

<script>
export default {
  name: "LandingComponent",
};
</script>

<style>
body {
  margin: 0;
  overflow: hidden;
}

.text {
  background-color: #0A0D14;
}

.landing {
  display: grid;
  grid-template-columns: 3fr 5fr;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

.headline {
  margin-top: 175px;
}

.image img {
  height: 100%;
  width: 100%;
  object-fit: cover;
  object-position: right;
}

h1 {
  color: #FFF;
  font-family: 'Roboto', sans-serif;
  font-size: 128px;
  font-style: normal;
  font-weight: 900;
  line-height: 150px;
  margin: 0;
  margin-left: 101px;


}

.powBy p {
  color: #544F69;
  font-family: 'Roboto', sans-serif;
  font-size: 20px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  margin-left: 101px;
  margin-top: 0;

}

#love{
  color: #FB0048;
}

span {
  color: #67FF64;
}
</style>

