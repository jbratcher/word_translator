<template>
  <div id="app" class="container">
    <About></About>
    <h1>Word Translator</h1>
    <TranslateForm  v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
    <h5>Powered by Vue.js & Yandex Translate API</h5>
    <AboutButton></AboutButton>
  </div>
</template>

<script>

import About from "./components/About"
import TranslateForm from "./components/TranslateForm"
import TranslateOutput from "./components/TranslateOutput"
import AboutButton from "./components/AboutButton"

export default {
  name: "app",
  components: {
    About, TranslateForm, TranslateOutput, AboutButton
  },
  data: { 
    function() {
      return {
        translatedText: ""
      };
    },
    seen: false
  },
  created() {
    this.translatedText = "Translation";
  },
  methods: {
    translateText: function(text, language) {
    this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170927T013614Z.0398812bbce63b32.71a2a2d1a3dc29ad889789d7ca354e2439180293&lang="+language+"&text=" + text)
    .then((response) => {
      this.translatedText = response.body.text[0];
    });
    }
  }
};

</script>

<style src="../src/css/styles.css"  type="text/css"></style>