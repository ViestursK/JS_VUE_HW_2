<template>
  <div class="aboutMe">
    <div class="edit">
      <h1>ABOUT ME</h1>
      <div class="seperator">|</div>
      <button @click="toggleFormEditing">{{ editFormButtonLabel }}</button>
    </div>

    <FormComponent :disabled="isFormDisabled" />
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'AboutMeComponent',
  setup() {
    const isFormEditing = ref(false);

    const toggleFormEditing = () => {
      isFormEditing.value = !isFormEditing.value;
    };

    return {
      isFormEditing,
      toggleFormEditing,
    };
  },
  computed: {
    editFormButtonLabel() {
      return this.isFormEditing ? 'CANCEL' : 'EDIT FORM';
    },
    isFormDisabled() {
      return !this.isFormEditing;
    },
  },
};
</script>

<style scoped>
#body {
  display: grid;
  grid-template-columns: 396px auto;
  height: 100vh;
}

.aboutMe {
  height: 100%;
  background: #191621;
}

.aboutMe h1 {
  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
  margin: 0;
  margin-left: 40px;
}

.edit {
  display: flex;
  justify-content: start;
  align-items: center;
  margin: 0;
  margin-top: 30px;

}

.seperator {
  margin-left: 20px;
  margin-right: 20px;
  color: #FFF;
  font-size: 30px;
}

button {
  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  width: 128px;
  padding-left: 15px;
  padding-right: 15px;
  background-color: #8645E8;
}

button.cancel {
  background-color: #e74c3c;
}

h1 {
  color: #FFF;
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-style: normal;
  font-weight: 900;
  line-height: normal;
}
</style>