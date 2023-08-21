<template>
  <q-btn class="button q-ma-md"
         :color="color"
         :flat="flat"
         :label="label"/>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "BaseButton",

  props:{
    label:{
      type: String,
    },
    color:{
      type: String,
      default: "green",
    },
    flat:{
      type: Boolean,
    }
  }
})
</script>



<style scoped lang="scss">

</style>
