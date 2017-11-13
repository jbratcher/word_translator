<template>
    <div class="row justify-content-center" id="TranslateForm">
      <div class="col">
            <form id="transForm" v-on:submit="formSubmit">
                <div class="form-group">
                    <input class="form-control form-control-lg pl-3" type="text" v-model="textToTranslate" placeholder="Enter word to translate">
                </div>
                <div class="form-group">
                    <select class="form-control form-control-lg pl-3" v-model="language">
                        <option value="es">Spanish</option>
                        <option value="fr">French</option>
                        <option value="zh">Chinese</option>
                        <option value="ga">Irish</option>
                        <option value="ru">Russian</option>
                    </select>
                </div>
                <div class="form-group">
                    <input class="btn btn-primary btn-large d-block w-100" type="submit" value="Translate">
                </div>
            </form>
        </div>
    </div>
</template>

<script>

export default {
  name: 'translateForm',
  data() {
      return {
          textToTranslate:""
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

<style>



</style>
