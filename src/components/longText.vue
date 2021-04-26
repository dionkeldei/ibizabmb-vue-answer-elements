<template lang="html">
  <div class="">
    <textarea class="uk-textarea" rows="3" v-model="value"></textarea>
  </div>
</template>

<script>
export default {
  name: 'longText',
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
  }
}
</script>

<style lang="css" scoped>
</style>
