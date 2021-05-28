<template>
  <div>
      <select v-model="countryCod">
        <option selected="selected">ru</option>
        <option>am</option>
        <option>de</option>
      </select>
      <input type="tel" v-mask="maskaInput" :key="maskaInput"/>
      <div>{{ maskaInput }}</div>
  </div>
</template>

<script>

export default {
  name: "App",

  data() {
    return {
      maskCode: {
        ru: "(999) 999-99-99",
        am: "999 999999",
        de: "99999 9999999",
      },
      countryCod: 'ru',
    };
  },
  computed: {
    maskaInput() {
      let maska = this.maskCode[this.countryCod];
      return maska;
    }
  },
};
</script>
