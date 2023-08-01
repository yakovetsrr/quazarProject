<template>
  <q-select
      v-model="value"
      class="base-select"
      :options="options"
      :label="label"
      outlined
      use-input
      stack-label
      emit-value
      dense
      clearable
    >
    <template #no-option>
      <div>Нет данных</div>
    </template>
  </q-select>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "BaseSelect",

  props: {
    modelValue: {
      type: String,
      required: true,
    },
    options: {
      type: Array,
      required: true,
      default: () => [],
    },
    label: {
      type: String,
    }
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
.base-select {
  overflow: hidden;
}
</style>
