<template>
    <q-input
      v-model="value"
      border
      clearable
      outlined
      class="q-ma-md"
      dense
      :debounce="debounce"
      :placeholder="placeholder">
      <template #append>
          <slot name="append"/>
      </template>
    </q-input>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "BaseInput",

  props: {
    placeholder: {
      type: String,
    },
    modelValue: {
      type: String,
      required: true,
    },
    debounce: {
      type: Number,
    },
  },
  emits: ['update:modelValue'],

  computed:{
    value:{
      get(){
        return this.modelValue;
      },
      set(value){
        this.$emit("update:modelValue", value);
      },
    }
  }
})
</script>

<style scoped lang="scss">

</style>
