<template lang="html">
  <div class="">
    <div v-for="(field,i) in element.fields" :key="i">
      <label>
        <input :value="field.value" class="uk-radio" :name="'ibiza_radio_answer_'+element.index" type="radio" v-model="value"/> {{field.text}}
      </label>
      <br>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ibizaSelectElement',
  props: {
    element: Object
  },
  methods: {
  },
  computed: {
    value: {
      get: function () {
        if(this.element.value != undefined){
          return this.element.value
        }
        return null
      },
      set: function (val) {
        this.$emit('change',val,this.element.index)
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
