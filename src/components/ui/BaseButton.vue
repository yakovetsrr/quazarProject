<template>
  <q-btn class="button q-ma-md"
         color="green"
         text-color="white"
         :label="label"/>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "BaseButton",

  props:{
    label:{
      type: String,
    }
  }
})
</script>



<style scoped lang="scss">

</style>
