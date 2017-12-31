<template>
        <form id="transForm" v-on:submit="formSubmit">
            <input type="text" v-model="textToTranslate" placeholder="Enter a word, phrase, or sentence...">
            <select v-model="language">
                <option value="es">Spanish</option>
                <option value="fr">French</option>
                <option value="zh">Chinese</option>
                <option value="ga">Irish</option>
                <option value="ru">Russian</option>
            </select>
            <input class="btn" type="submit" value="Translate">
        </form>
</template>

<script>

export default {
  name: 'translateForm',
  data() {
      return {
          textToTranslate:"",
          language:""
      }
  },
  created() {
      this.language = "es"
  },
  methods: {
      formSubmit(e) {
          this.$emit("formSubmit", this.textToTranslate, this.language)
          e.preventDefault();
      }
  }
}

</script>

<style src="../css/styles.css"  type="text/css"></style>

