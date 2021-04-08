<template>
  <div class="ibizabmb-answer-elements">
     <selection v-if="element.type == 'select'" :element="element" @change="change"/>
     <radio v-if="element.type == 'radio'" :element="element" @change="change"/>
     <radio-comment v-if="element.type == 'radio-comment'" :element="element" @change="change"/>
     <checkboxes v-if="element.type == 'checkbox'" :element="element" @change="change"/>
     <short-text v-if="element.type == 'text'" :element="element" @change="change"/>
     <long-text v-if="element.type == 'longText'" :element="element" @change="change"/>
  </div>
</template>

<script>
import selection from '@/components/select.vue'
import radio from '@/components/radio.vue'
import radioComment from '@/components/radio_comment.vue'
import checkboxes from '@/components/checkbox.vue'
import shortText from '@/components/shortText.vue'
import longText from '@/components/longText.vue'
export default {
  name: 'ibiza-answer-elements',
  /*data () {
    return {
      element: {
        index: 56,
        type: 'longText',
        fields: [
          {
            text: 'campo1',
            value: 'valor1'
          },
          {
            text: 'campo2',
            value: 'valor2'
          }
        ],
        value: 'Este texto es para el textarea\ny otro renglon'
      }
    }
  },*/
  props:{
    element: Object
  },
  components: {
    selection,
    radio,
    radioComment,
    checkboxes,
    shortText,
    longText
  },
  methods: {
    change: function (val, index) {
      this.$emit('change',val,index)
    }
  }
}
</script>

<style>
</style>
