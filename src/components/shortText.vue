<template lang="html">
  <div class="">
    <input class="uk-input" v-model="value"/>
  </div>
</template>

<script>
export default {
  name: 'shortText',
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
        return ''
      },
      set: function (val) {
        this.$emit('change',val,this.element.index)
      }
    }
  },
  watch: {
  }
}
</script>

<style lang="css" scoped>
</style>
