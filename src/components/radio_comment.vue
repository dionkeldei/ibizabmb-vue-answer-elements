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
      value: {
        value: 0,
        text: null
      }
    }
  },
  props: {
    element: Object
  },
  methods: {
  },
  computed: {
    getValue: function () {
        if(this.element.value != undefined){
          return this.element.value
        }
        return {value: null,text: ''}
    },
    innerValue: function () {
      return this.value.value
    },
    innerText: function () {
      return this.value.text
    }
  },
  mounted () {
    this.value = this.getValue
  },
  watch: {
    innerValue: function () {
      this.$emit('change',this.value,this.element.index)
    },
    innerText: function () {
      this.$emit('change',this.value,this.element.index)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
