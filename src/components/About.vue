<template>
    <div id="about" v-show="show">
      <h2>About Word Translator</h2>
      <p>Word Translator is a Vue SPA built using the Yandex Translate API.  It was born out of a tutorial created by Brad Traversy and continues to live on as a project to sharpen my skills wth a variety of tech including Node.js, Express.js, jQuery, CSS, and HTML.</p>
      <a href="https://github.com/jbratcher/word_translator">Github project page</a>
    </div>
</template>

<script>

import AboutButton from "./AboutButton";

export default {
  components: AboutButton,
  name: 'about',
  show: true
};

</script>

<style src="../css/styles.css"  type="text/css"></style>

