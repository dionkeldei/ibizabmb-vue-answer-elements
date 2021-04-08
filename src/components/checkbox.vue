<template lang="html">
  <div class="">
    <div v-for="(field,i) in element.fields" :key="i">
      <label>
        <input :value="field.value" class="uk-checkbox" :name="'ibiza_checkbox_answer_'+element.index" type="checkbox" v-model="values[i]"/> {{field.text}}
      </label>
      <br>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ibizaCheckboxElement',
  data () {
    return {
      values: []
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
        var arr = []
        for(var i=0;i<this.element.fields.length;i++){
          arr.push(false)
        }
        console.log(arr)
        return arr
    }
  },
  mounted() {
    this.values = this.getValue
  },
  watch: {
    values: function (val) {
      this.$emit('change',val,this.element.index)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
