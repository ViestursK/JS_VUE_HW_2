<template>
  <div class="formComponent">
    <form>
      <div>
        <label for="firstName">First name</label>
        <input type="text" id="firstName" v-model="user.name" :disabled="disabled "
          :class="{ 'editable-input': !disabled }" />
      </div>
      <div>
        <label for="lastName">Last name</label>
        <input type="text" id="lastName" v-model="user.surname" :disabled="disabled"
          :class="{ 'editable-input': !disabled }" />
      </div>
      <div>
        <label for="studentCode">Student code</label>
        <input type="text" id="studentCode" v-model="user.code" :disabled="disabled"
          :class="{ 'editable-input': !disabled }" />
      </div>
      <div>
        <label for="loggedAt">Logged in at</label>
        <ul>
          <li>{{ formattedLastLogin }}</li>
        </ul>
      </div>
    </form>
  </div>
</template>

<script>
import { ref } from 'vue';
import { store } from '../store';

export default {
  computed: {
    formattedLastLogin() {
      const timestamp = store.user.time;
      if (timestamp) {
        const date = new Date(timestamp);
        const day = date.getDate();
        const month = date.getMonth() + 1; // Months are 0-indexed
        const year = date.getFullYear();
        const hours = date.getHours();
        const minutes = date.getMinutes();

        return `${day}.${month}.${year} - ${hours}:${minutes.toString().padStart(2, '0')}`;
      }
      return 'N/A'; // Handle the case when the timestamp is not available
    }
  },
  props: {
    disabled: Boolean,
  },
  setup() {
    const user = ref(store.user);

    return {
      user,
    };
  },
};
</script>

<style scoped>
.formComponent {
  display: flex;
  justify-content: start;
  align-items: center;
}

form {
  margin-left: 40px;
  margin-top: 64px;
}

label {
  display: block;
  color: rgba(255, 255, 255, 0.50);
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
}

input {
  width: 466px;
  height: 42px;
  flex-shrink: 0;
  border-radius: 4px;
  background: #22202B;
  border: none;
  margin-bottom: 40px;
  margin-top: 12px;
  padding: 15px;
  padding-top: 10px;
  padding-bottom: 10px;

  color: rgba(255, 255, 255, 0.70);
  font-family: 'Montserrat', sans-serif;
  font-size: 18px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  margin-top: 20px;
}

li {
  color: #544F69;
  font-family: 'Montserrat', sans-serif;
  font-size: 18px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  margin: 0;
}

.editable-input {
  background: #464157;
}
</style>