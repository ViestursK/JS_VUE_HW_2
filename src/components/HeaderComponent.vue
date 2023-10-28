<template>
  <div class="header" :class="{ 'def-header': !store.isLoggedIn }">
    <div class="logo">
      <img src="../assets/logo.svg" />
      <h2>KRAKEN.FM</h2>
    </div>
    <div class="controlPanel">
      <div v-if="store.isLoggedIn" class="user">
        <span class="avatar"></span>
        <h3>{{ fullName }}</h3>
        <div class="seperator">|</div>

      </div>
      <button @click="store.loginManager()">
        {{ store.isLoggedIn ? 'LOGOUT' : 'LOGIN' }}
      </button>
    </div>
  </div>
</template>

<script>
import { store } from '../store';

export default {
  data() {
    return {
      store
    }
  },
  computed: {
    fullName() {
      return `${store.user.name} ${store.user.surname}`;
    }
  }
}
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 71px;
  border-bottom: 1px solid #916DDC80;
  background: #8645E8;
}

.def-header {
  background-color: #0A0D14;
}

.controlPanel {
  display: flex;
  align-items: center;
}

img {
  width: 51px;
  height: 51px;
  flex-shrink: 0;
}

.logo {
  margin-left: 40px;
  display: flex;
  align-items: center;

}

.user {
  display: flex;
  align-items: center;
}

.avatar {
  height: 35px;
  width: 35px;
  border-radius: 100%;
  background-color: #D7B8FF;
}

h3 {
  margin-left: 10px;
  color: #FFF;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
}

h2 {
  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 24px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
}

button {
  width: 99px;
  height: 33px;
  flex-shrink: 0;
  border-radius: 50px;
  background: #391372;
  border: none;
  margin-right: 26px;
  cursor: pointer;

  color: #D7B8FF;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  padding-left: 15px;
  padding-right: 15px;
}

.seperator {
  margin-left: 20px;
  margin-right: 20px;
  color: #FFF;
  font-size: 30px;
}
</style>
