<template>
  <div class="ibizabmb-answer-elements">
     <selection v-if="element.type == 'select'" :element="element" @change="change"/>
     <radio v-if="element.type == 'radio'" :element="element" @change="change"/>
     <radio-comment v-if="element.type == 'radio-comment'" :element="element" @change="change"/>
     <checkboxes v-if="element.type == 'checkbox'" :element="element" @change="change"/>
  </div>
</template>

<script>
import selection from '@/components/select.vue'
import radio from '@/components/radio.vue'
import radioComment from '@/components/radio_comment.vue'
import checkboxes from '@/components/checkbox.vue'
export default {
  name: 'ibiza-answer-elements',
  data () {
    return {
      element: {
        index: 56,
        type: 'checkbox',
        fields: [
          {
            text: 'campo1',
            value: 'valor1'
          },
          {
            text: 'campo2',
            value: 'valor2'
          }
        ]
      }
    }
  },
  components: {
    selection,
    radio,
    radioComment,
    checkboxes
  },
  methods: {
    change: function (val, index) {
      console.log(val)
      console.log(index)
    }
  }
}
</script>

<style>
</style>
