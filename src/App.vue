<template>
  <div>
      <select v-model="countryCod">
        <option v-for="item in phonesCodes" :value="item.code" :key="item.code">{{ item.code }}</option>
      </select>
      <input type="tel" v-mask="maskaInput" :key="maskaInput.mask"/>
      <div>{{ maskaInput }}</div>
  </div>
</template>

<script>

export default {
  name: "App",

  data() {
    return {
      phonesCodes: {
        am: { code: 'am', name: 'Армения', dialCode: 374, example: '999 999999' },
        az: { code: 'az', name: 'Азербайджан', dialCode: 994, example: '999 999 99 99' },
        by: { code: 'by', name: 'Беларусь', dialCode: 375, example: '999 999-99-99' },
        ee: { code: 'ee', name: 'Эстония', dialCode: 372, example: '9999 9999' },
        ge: { code: 'ge', name: 'Грузия', dialCode: 995, example: '999 99 99 99' },
        kg: { code: 'kg', name: 'Кыргызстан', dialCode: 996, example: '9999 999 999' },
        lv: { code: 'lv', name: 'Латвия', dialCode: 371, example: '99 999 999' },
        lt: { code: 'lt', name: 'Литва', dialCode: 370, example: '(9-999) 99999' },
        md: { code: 'md', name: 'Молдавия', dialCode: 373, example: '9999 99 999' },
        ru: { code: 'ru', name: 'Россия', dialCode: 7, example: '(999) 999-99-99' },
        tj: { code: 'tj', name: 'Таджикистан', dialCode: 992, example: '999 99 9999' },
        tm: { code: 'tm', name: 'Туркменистан', dialCode: 993, example: '(8 999) 9-99-99' },
        ua: { code: 'ua', name: 'Украина', dialCode: 380, example: '099 999 9999' },
        uz: { code: 'uz', name: 'Узбекистан', dialCode: 998, example: '8 99 999 99 99' },
        de: { code: 'de', name: 'Германия', dialCode: 49, example: '99999 9999999' },
        kz: { code: 'kz', name: 'Казахстан', dialCode: 7, example: '(999) 999-99-99' },
      },
      countryCod: 'ru',
    };
  },
  computed: {
    maskaInput() {
      return {
        mask: this.phonesCodes[this.countryCod].example,
        clearMaskOnLostFocus: false,
      };
    },
  },
};
</script>
