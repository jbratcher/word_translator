<template>
  <div id="app" class="container">
        <h1>Word Translator</h1>
        <TranslateForm  v-on:formSubmit="translateText"></TranslateForm>
        <TranslateOutput v-text="translatedText"></TranslateOutput>
        <h5>Powered by Vue.js & Yandex Translate API</h5>
  </div>
</template>

<script>

import TranslateForm from "./components/TranslateForm"
import TranslateOutput from "./components/TranslateOutput"

export default {
  name: "app",
  components: {
    TranslateForm, TranslateOutput
  },
  data: function() {
    return {
      translatedText: ""
    };
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
}

</script>

<style src="../src/assets/styles.css"  type="text/css"></style>