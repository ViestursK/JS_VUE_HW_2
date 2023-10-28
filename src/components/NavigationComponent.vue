<template>
  <nav id="navigaton" v-if="store.isLoggedIn">
    <ol>
      <li v-for="(link, index) in routes" :key="index" :class="{ active: $route.path === link.path }">
        <router-link :to="link.path">{{ link.name }}</router-link>
      </li>
    </ol>
  </nav>
</template>


<script>
import { store } from '../store';

export default {
  data() {
    return {
      routes: [
        {
          name: 'Home',
          path: '/home'
        },
        {
          name: 'About me',
          path: '/about-me'
        }
      ],
      store
    }
  },
}
</script>

<style>
#navigaton {
  padding: 1rem;
  background: #22202B;
  justify-content: center;
}

li {
  margin-left: 20px;
}

ol {
  list-style-type: none;
  padding: 0px;
}

li.active {
  background: url('../assets/Rectangle 11.png') no-repeat left center;
}

a {
  display: block;
  padding: 10px;
  margin-bottom: 5px;

  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 18px;
  font-style: normal;
  font-weight: 800;
  line-height: normal;
  text-decoration: none;
}
</style>