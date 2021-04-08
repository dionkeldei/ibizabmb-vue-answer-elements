<template>
  <div class="ibizabmb-answer-elements">
     <selection v-if="element.type == 'select'" :element="element" @change="change"/>
     <radio v-if="element.type == 'radio'" :element="element" :index="element.name" @change="change"/>
     <radio-comment v-if="element.type == 'radio-comment'" :element="element" :index="element.name" @change="change"/>
  </div>
</template>

<script>
import selection from '@/components/select.vue'
import radio from '@/components/radio.vue'
import radioComment from '@/components/radio_comment.vue'
export default {
  name: 'ibiza-answer-elements',
  data () {
    return {
      element: {
        index: 56,
        type: 'radio-comment',
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
    radioComment
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
