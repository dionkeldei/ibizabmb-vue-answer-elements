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
