<template lang="html">
  <div class="">
    <div v-for="(field,i) in element.fields" :key="i">
      <label>
        <input :value="field.value" class="uk-radio" :name="'ibiza_radio_answer_'+element.index" type="radio" v-model="value.value"/> {{field.text}}
      </label>
      <br>
    </div>
    <textarea v-model="value.text" class="uk-textarea" rows="3"></textarea>
  </div>
</template>

<script>
export default {
  name: 'ibizaSelectElement',
  data () {
    return {
    }
  },
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
        return {value: null,text: ''}
      },
      set: function (val) {
        this.$emit('change',val,this.element.index)
      }
    },
    innerValue: function () {
      return this.value.value
    },
    innerText: function () {
      return this.value.text
    }
  },
  watch: {
  }
}
</script>

<style lang="css" scoped>
</style>
