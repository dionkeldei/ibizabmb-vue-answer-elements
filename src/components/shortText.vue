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
      value: ''
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
        return ''
    }
  },
  mounted() {
    this.value = this.getValue
  },
  watch: {
    value: function (val) {
      this.$emit('change',val,this.element.index)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
