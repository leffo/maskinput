<template>
  <div>
    <div>
      <VuePhoneNumberInput v-model="yourValue" :translations="translations" />
      <br /><br />
      <select v-model="countryCod">
        <option selected>ru</option>
        <option>am</option>
        <option>de</option>
      </select>
      <input type="tel" v-mask="maska" />
    </div>
  </div>
</template>

<script>
import VuePhoneNumberInput from "vue-phone-number-input";
import "vue-phone-number-input/dist/vue-phone-number-input.css";

export default {
  name: "App",
  components: { VuePhoneNumberInput },
  directives: {},

  data() {
    return {
      yourValue: "",
      translations: {
        countrySelectorLabel: "Код страны",
        countrySelectorError: "Выберите страну",
        phoneNumberLabel: "Телефонный номер",
        example: "Пример :",
      },
      maskCode: {
        ru: "(999) 999-99-99",
        am: "999 999999",
        de: "99999 9999999",
      },
      phonesCodes: {
        am: {
          code: "am",
          name: "Армения",
          dialCode: 374,
          example: "077123456",
        },
        az: {
          code: "az",
          name: "Азербайджан",
          dialCode: 994,
          example: "0401234567",
        },
        by: {
          code: "by",
          name: "Беларусь",
          dialCode: 375,
          example: "80294911911",
        },
        ee: { code: "ee", name: "Эстония", dialCode: 372, example: "51234567" },
        ge: { code: "ge", name: "Грузия", dialCode: 995, example: "555123456" },
        kg: {
          code: "kg",
          name: "Кыргызстан",
          dialCode: 996,
          example: "700123456",
        },
        lv: { code: "lv", name: "Латвия", dialCode: 371, example: "21234567" },
        lt: { code: "lt", name: "Литва", dialCode: 370, example: "861234567" },
        md: {
          code: "md",
          name: "Молдавия",
          dialCode: 373,
          example: "062112345",
        },
        ru: { code: "ru", name: "Россия", dialCode: 7, example: "9123456789" },
        tj: {
          code: "tj",
          name: "Таджикистан",
          dialCode: 992,
          example: "8917123456",
        },
        tm: {
          code: "tm",
          name: "Туркменистан",
          dialCode: 993,
          example: "866123456",
        },
        ua: {
          code: "ua",
          name: "Украина",
          dialCode: 380,
          example: "0391234567",
        },
        uz: {
          code: "uz",
          name: "Узбекистан",
          dialCode: 998,
          example: "8912345678",
        },
        de: {
          code: "de",
          name: "Германия",
          dialCode: 49,
          example: "6912345678",
        },
        kz: {
          code: "kz",
          name: "Казахстан",
          dialCode: 7,
          example: "7710009998",
        },
      },
      countryCod: "ru",
      maska: this.maskCode,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
