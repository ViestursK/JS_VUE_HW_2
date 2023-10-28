<template>
  <div class="songFilter">
    <p>Sort by:
    </p>
    <button @click="applyFilter('None')" :class="{ active: activeFilter === 'None' }">None</button>
    <button @click="applyFilter('Name')" :class="{ active: activeFilter === 'Name' }">Name</button>
    <button @click="applyFilter('Artist')" :class="{ active: activeFilter === 'Artist' }">Artist</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'SongFilterComponent',
  props: {
    onFilterChanged: Function,
  },
  setup(props) {

    const activeFilter = ref('None');

    const applyFilter = (filter) => {
      activeFilter.value = filter;
      props.onFilterChanged(filter);
    };

    return {
      activeFilter,
      applyFilter,
    };
  },
};
</script>

<style scoped>
.songFilter {
  display: flex;
  align-content: center;
}

.songFilter p {
  color: rgba(255, 255, 255, 0.80);
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  margin: 0;
  padding-left: 8px;
  margin-right: 10px;
  align-self: center;
}

button {
  margin: 5px;
  padding: 5px 10px;
  background-color: transparent;
  color: #fff;
  border: none;
  cursor: pointer;
  font-family: 'Montserrat', sans-serif;
  font-size: 14px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
}

.active {
  color: #FB0048;
  border-radius: 50px;
  background: rgba(251, 0, 72, 0.20);
}
</style>