<template>
  <div class="ibizabmb-answer-elements">
     <selection v-if="element.type == 'select'" :element="element" @change="change"/>
     <radio v-if="element.type == 'radio'" :element="element" :index="element.name" @change="change"/>
  </div>
</template>

<script>
import selection from '@/components/select.vue'
import radio from '@/components/radio.vue'
export default {
  name: 'ibiza-answer-elements',
  data () {
    return {
      element: {
        index: 56,
        type: 'radio',
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
    radio
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
