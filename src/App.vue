<template>
  <div>
      <select v-model="countryCod">
        <option v-for="item in phonesCodes" :value="item.code" :key="item.code">{{ item.code }}</option>
      </select>
    <input type="tel" v-maske="maskaInput" />
      <div>{{ maskaInput }}</div>
  </div>
</template>

<script>
import maske from 'vue-r-mask'

export default {
  name: "App",

  data() {
    return {
      phonesCodes: {
        am: { code: 'am', name: 'Армения', dialCode: 374, example: "/\\d{3} \\d{6}/" },
        az: { code: 'az', name: 'Азербайджан', dialCode: 994, example: "/\\d{3} \\d{3} \\d{2} \\d{2}/" },
        by: { code: 'by', name: 'Беларусь', dialCode: 375, example: "/\\d{3} \\d{3}-\\d{2}-\\d{2}/" },
        ee: { code: 'ee', name: 'Эстония', dialCode: 372, example: "/\\d{4} \\d{4}/" },
        ge: { code: 'ge', name: 'Грузия', dialCode: 995, example: "/\\d{3} \\d{2} \\d{2} \\d{2}/" },
        kg: { code: 'kg', name: 'Кыргызстан', dialCode: 996, example: "/\\d{4} \\d{3} \\d{3}/" },
        lv: { code: 'lv', name: 'Латвия', dialCode: 371, example: "/\\d{2} \\d{3} \\d{3}/" },
        lt: { code: 'lt', name: 'Литва', dialCode: 370, example: "/\\(\\d-\\d{3}\\) \\d{5}/"},
        md: { code: 'md', name: 'Молдавия', dialCode: 373, example: "/\\d{4} \\d{2} \\d{3}/" },
        ru: { code: 'ru', name: 'Россия', dialCode: 7, example: /\(\d{3}\) \d{3}-\d{2}-\d{2}/ },
        tj: { code: 'tj', name: 'Таджикистан', dialCode: 992, example: "/\\d{3} \\d{2} \\d{4}/" },
        tm: { code: 'tm', name: 'Туркменистан', dialCode: 993, example: "/\\(8 \\d{3}\\) \\d{1}-\\d{2}-\\d{2}/"},
        ua: { code: 'ua', name: 'Украина', dialCode: 380, example: "/0\\d{2} \\d{3} \\d{4}/" },
        uz: { code: 'uz', name: 'Узбекистан', dialCode: 998, example: "/8\\d{2} \\d{3} \\d{2} \\d{2}/"},
        de: { code: 'de', name: 'Германия', dialCode: 49, example: "/\\d{5} \\d{6}/" },
        kz: { code: 'kz', name: 'Казахстан', dialCode: 7, example: "/\\(\\d{3}\\) \\d{3}-\\d{2}-\\d{2}/" },
      },
      countryCod: 'ru',
    };
  },
  computed: {
    maskaInput() {
      return this.phonesCodes[this.countryCod].example
    },
  },
  directives: {
    maske: maske,
  },

};
</script>
