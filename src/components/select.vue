<template lang="html">
  <div class="">
    <select class="uk-select" v-model="value">
      <option :value="null" disabled>Selecciona una opción ...</option>
      <option v-for="(field,i) in element.fields" :key="i" :value="field.value">{{field.text}}</option>
    </select>
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
